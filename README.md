# Packerr Templates

 Packer template to create Google Cloud Virtual Machine images for use on different cloud providers.

## Create VM Image

1. Install Packer: https://developer.hashicorp.com/packer/tutorials/aws-get-started/get-started-install-cli

2. From IAM & Admin > Service Accounts in Google Cloud Console, create a new service account with the following permissions: 
   
   - Compute Engine Instance Admin (v1)
   - Service Account User
  
3. Create a new key with JSON file and place in the Packer project directory and change the `"account_file"` in each template accordingly. 

4.  To create a new VM Image with SLEAP dependencies and Google Chrome Remote Desktop installed, first template must be validated using this command

    ```
    packer validate template-crd.json
    ```

5. Create an image

    Run this command to create an image with Google Chrome Remote Desktop. This image will enable users to connect to the VM instance of that image using Google Chrome Remote Desktop. 

    ```
    packer build template-crd.json
    ```