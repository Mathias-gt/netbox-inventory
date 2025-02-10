# NetBox Inventory in Ansible Automation Platform

## Configuring Credential Types in Ansible Automation Platform

To use `netbox-inventory`, you need to create a custom **Credential Type** in NetBox. Follow these steps:

### 1. Create a New Credential Type  

Navigate to **Automation** → **Credential Types** and click **Add**.

#### **Name:**  
`NetBox`

#### **Input Configuration (YAML):**  
```yaml
fields:
  - id: NETBOX_API
    type: string
    label: NetBox URL
    secret: false
  - id: NETBOX_API_KEY
    type: string
    label: NetBox API Token
    secret: true
```


#### **Injector Configuration (YAML):**  
```yaml
env:
  NETBOX_API: '{{ NETBOX_API }}'
  NETBOX_API_KEY: '{{ NETBOX_API_KEY }}'
```
