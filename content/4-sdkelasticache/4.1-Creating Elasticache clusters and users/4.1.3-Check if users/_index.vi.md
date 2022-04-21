---
title : "Kiểm tra nhóm người dùng"
date :  "`r Sys.Date()`" 
weight : 3
chapter : false
pre : " <b> 4.1.3 </b> "
---

Với RBAC, bạn tạo người dùng và gán cho họ các quyền cụ thể bằng cách sử dụng một chuỗi truy cập. Bạn chỉ định người dùng vào các nhóm người dùng phù hợp với một vai trò cụ thể (quản trị viên, nguồn nhân lực) sau đó được triển khai cho một hoặc nhiều ElastiCache for Redis replication groups. Bằng cách này, bạn có thể thiết lập ranh giới bảo mật giữa các máy khách sử dụng cùng một nhóm hoặc nhóm sao chép Redis và ngăn các máy khách truy cập dữ liệu của nhau.

1. Tạo một file python có tên UserAndUserGroups.py
2. Sao chép chương trình sau và dán vào file có tên UserAndUserGroups.py.

```
import boto3
import logging

logging.basicConfig(level=logging.INFO)
client = boto3.client('elasticache')

def check_user_exists(UserId):
    """Checks if UserId exists

    Returns True if UserId exists, otherwise False
    :param UserId: Elasticache User ID
    :return: True|False
    """
    try:
        response = client.describe_users(
            UserId=UserId,
        )
        if response['Users'][0]['UserId'].lower() == UserId.lower():
            return True
    except Exception as e:
        if e.response['Error']['Code'] == 'UserNotFound':
            logging.info(e.response['Error'])
            return False
        else:
            raise

def check_group_exists(UserGroupId):
    """Checks if UserGroupID exists

    Returns True if Group ID exists, otherwise False
    :param UserGroupId: Elasticache User ID
    :return: True|False
    """

    try:
        response = client.describe_user_groups(
            UserGroupId=UserGroupId
        )
        if response['UserGroups'][0]['UserGroupId'].lower() == UserGroupId.lower():
            return True
    except Exception as e:
        if e.response['Error']['Code'] == 'UserGroupNotFound':
            logging.info(e.response['Error'])
            return False
        else:
            raise

def create_user(UserId=None,UserName=None,Password=None,AccessString=None):
    """Creates a new user

    Returns the ARN for the newly created user or the error message
    :param UserId: Elasticache user ID. User IDs must be unique
    :param UserName: Elasticache user name. Elasticache allows multiple users with the same name as long as the associated user ID is unique.
    :param Password: Password for user. Must have at least 16 chars.
    :param AccessString: Access string with the permissions for the user. For details refer to https://docs..amazon.com/AmazonElastiCache/latest/red-ug/Clusters.RBAC.html#Access-string
    :return: user ARN
    """
    try:
        response = client.create_user(
            UserId=UserId,
            UserName=UserName,
            Engine='Redis',
            Passwords=[Password],
            AccessString=AccessString,
            NoPasswordRequired=False
        )
        return response['ARN']
    except Exception as e:
        logging.info(e.response['Error'])
        return e.response['Error']

def create_group(UserGroupId=None, UserIds=None):
    """Creates a new group.
    A default user is required (mandatory) and should be specified in the UserIds list

    Return: Group ARN
    :param UserIds: List with user IDs to be associated with the new group. A default user is required
    :param UserGroupId: The ID (name) for the group
    :return: Group ARN
    """
    try:
        response = client.create_user_group(
            UserGroupId=UserGroupId,
            Engine='Redis',
            UserIds=UserIds
        )
        return response['ARN']
    except Exception as e:
        logging.info(e.response['Error'])


if __name__ == '__main__':
    
    groupName='mygroup2'
    userName = 'myuser2'
    userId=groupName+'-'+userName

    # Creates a new user if the user ID does not exist.
    for tmpUserId,tmpUserName in [ (userId,userName), (groupName+'-default','default')]:
        if not check_user_exists(tmpUserId):
            response=create_user(UserId=tmpUserId, UserName=tmpUserName,Password='MyStrongPasswordWithNumbers',AccessString='on ~* +@all')
            logging.info(response)
        # assigns the new user ID to the user group
    if not check_group_exists(groupName):
        UserIds = [ userId , groupName+'-default']
        response=create_group(UserGroupId=groupName,UserIds=UserIds)
        logging.info(response)

```

3. Để chạy chương trình, hãy nhập lệnh sau:

```
python UserAndUserGroups.py

```

Trường hợp không chạy được chương trình, ta sử dụng lệnh sau:

```
python "đường dẫn file UserAndUserGroups.py"

```
