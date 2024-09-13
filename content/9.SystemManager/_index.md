---
title: "Configuring System Manager Parameter Store"
date :  "`r Sys.Date()`" 
weight : 9
chapter : false
pre : " <b> 9. </b> "
---

In this section, we will configure **System Manager Parameter Store** to manage the parameters needed for the API system. Using Parameter Store helps you securely store and manage data, making it easily accessible across different applications.

## Access System Manager

From the AWS **console**, search for and access the **System Manager** service.

![Untitled](/images/System%20Manager%2081af2df204ae47228cfd929b014df79e/image.png)

### Access Parameter Store

Within the **System Manager** interface, navigate to **Parameter Store** to begin managing parameters.

![Untitled](/images/System%20Manager%2081af2df204ae47228cfd929b014df79e/image%201.png)

## Create a Parameter

Once inside the **Parameter Store** interface, proceed to create parameters by selecting **Create parameter**.

![Untitled](/images/System%20Manager%2081af2df204ae47228cfd929b014df79e/image%202.png)

Next, you will create 3 parameters as shown in the template.

![Untitled](/images/System%20Manager%2081af2df204ae47228cfd929b014df79e/image%203.png)

- Name the parameter **<StackName>**, which you can retrieve from **appconfig.json** in your system.

```text
/<StackName>/default/contextFooter/

/<StackName>/default/noContextFooter/

/<StackName>/default/promptHeader/
```

- For this lab, **Standard** is sufficient, as it is free.
- The parameter type should be **String**, and the **Data Type** should be **Text**.

![Untitled](/images/System%20Manager%2081af2df204ae47228cfd929b014df79e/image%204.png)

In the **value** section, access your source code and copy the necessary content into the parameter.

![Untitled](/images/System%20Manager%2081af2df204ae47228cfd929b014df79e/image%205.png)

Finally, click **Save** to complete the parameter creation process.