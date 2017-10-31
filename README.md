## Sample DNAC integration for Ansible

This is a sample collection of roles and playbooks leveraging the DNA Center REST API.

To use these playbooks you will need to edit the vars.yml file to include the correct credentials for your DNAC (I know I should move this to a vault)

I have written a couple of roles to "get/post/delete".

```buildoutcfg
$ ansible-playbook get_network_devices.yml 
 
PLAY [localhost] ***********************************************************************************************************************************************************************************

TASK [Gathering Facts] *****************************************************************************************************************************************************************************
ok: [localhost]

TASK [auth : Get Auth Cookie] **********************************************************************************************************************************************************************
ok: [localhost]

TASK [auth : Set cookie as fact] *******************************************************************************************************************************************************************
ok: [localhost]

TASK [auth : Check cookie] *************************************************************************************************************************************************************************
ok: [localhost] => {
    "cookie": "X-JWT-ACCESS-TOKEN=XAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9XXXXX.eyJzdWIiOiYYYYYxYYYYxODhiYjE2OTAwOTAyODBmMTYiLCJhdXRoU291cmNlIjoiaW50ZXJuYWwiLCJ0ZW5hbnROYW1lIjoiVE5UMCIsInJvbGVzIjpbIjU5ZjE1OWQ5MGIxMzRmYjQ0MjM0OWYwZiJdLCJ0ZW5hbnRJZCI6IjU5ZjE1YTE3OGJiMTY5MDA5MDI4MGYxNSIsImV4cCI6MTUwOTQxNjM1OSwidXNlcm5hbWUiOiJhZG1pbiJ9.BCMNyhYiDAmKEhT_zau6Uca9bobBF9Ztwi0ZjN48Y2c"
}

TASK [get : GET] ***********************************************************************************************************************************************************************************
ok: [localhost]

TASK [get : set response] **************************************************************************************************************************************************************************
ok: [localhost]

TASK [get : show response] *************************************************************************************************************************************************************************
skipping: [localhost]

TASK [show result] *********************************************************************************************************************************************************************************
ok: [localhost] => {
    "response": [
        {
            "apManagerInterfaceIp": "", 
            "associatedWlcIp": "", 
            "bootDateTime": "2017-10-02 15:42:04", 
            "collectionInterval": "Global Default", 
            "collectionStatus": "Managed", 
            "errorCode": null, 
            "errorDescription": null, 
            "family": "Switches and Hubs", 
            "hostname": "3650-dhcp", 
            "id": "05629e8a-83e9-4bc7-bd1b-fae82f472c5b", 
            "instanceUuid": "05629e8a-83e9-4bc7-bd1b-fae82f472c5b", 
            "interfaceCount": "160", 
            "inventoryStatusDetail": "<status><general code=\"SUCCESS\"/></status>", 
            "lastUpdateTime": 1509414452772, 
            "lastUpdated": "2017-10-31 01:47:32", 
            "lineCardCount": "3", 
            "lineCardId": "6d4603ef-7a8e-432e-b259-e0f
            <<snip>>
```