# Create an Azure IoT Hub and Device IDs

In this unit, we first create an IoT Hub, and then add a single device to that hub. To complete the unit, we record the connection strings needed for the coding part of this module.

As part of this course, we have already created an Azure IoT Hub and Device ID using the portal. This time around, we will use the Azure CLI to create the items we need.

1. Using a browser, open the [Azure Cloud Shell](https://shell.azure.com/) and login with the Azure subscription you are using for this course.

1. To ensure the Azure Cloud Shell is using **Bash**, ensure the dropdown selected value in the top-left is **Bash**.

1. To upload the setup script, in the Azure Cloud Shell toolbar, click **Upload/Download files** (fourth button from the right).

1. Before the Azure CLI can be used with commands for working with Azure IoT Hub, the **Azure IoT Extensions** need to be installed. To install the extension, run the following command:

    ```sh
    az extension add --name azure-cli-iot-ext
    ```

1. In the dropdown, select **Upload** and in the file selection dialog, navigate to the **lab-setup.azcli** file for this lab. Select the file and click **Open** to upload it.

    A notification will appear when the file upload has completed.

1. You can verify that the file has uploaded by listing the content of the current directory by entering the `ls` command.

1. To create a directory for this lab, move **lab-setup.azcli** into that directory, and make that the current working directory, enter the following commands:

    ```bash
    mkdir lab9
    mv lab-setup.azcli lab9
    cd lab9
    ```

1. To ensure the **lab-setup.azcli** has the execute permission, enter the following commands:

    ```bash
    chmod +x lab-setup.azcli
    ```

1. To edit the **lab-setup.azcli** file, click **{ }** (Open Editor) in the toolbar (second button from the right). In the **Files** list, select **lab9** to expand it and then select **lab-setup.azcli**.

    The editor will now show the contents of the **lab-setup.azcli** file.

1. In the editor, update the values of the `YourID` and `Location` variables. Set `YourID` to your initials and todays date - i.e. **CAH121119**, and set `Location` to the location that makes sense for your resources.

    > [!NOTE] The `Location` variable should be set to the short name for the location. You can see a list of the available locations and their short-names (the **Name** column) by entering this command:
    >
    > ```bash
    > az account list-locations -o Table
    > ```
    >
    > ```text
    > DisplayName           Latitude    Longitude    Name
    > --------------------  ----------  -----------  ------------------
    > East Asia             22.267      114.188      eastasia
    > Southeast Asia        1.283       103.833      southeastasia
    > Central US            41.5908     -93.6208     centralus
    > East US               37.3719     -79.8164     eastus
    > East US 2             36.6681     -78.3889     eastus2
    > ```

1. To save the changes made to the file and close the editor, click **...** in the top-right of the editor window and select **Close Editor**.

    If prompted to save, click **Save** and the editor will close.

    > [!NOTE] You can use **CTRL+S** to save at any time and **CTRL+Q** to close the editor.

1. To create a resource group named **AZ-220-RG**, create an IoT Hub named **AZ-220-HUB-{YourID}**, add a device with a Device ID of **SimulatedThermostat**, and display the device connection string, enter the following command:

    ```bash
    ./lab-setup.azcli
    ```

    This will take a few minutes to run. You will see JSON output as each step completes.

1. Once complete, the **Connection Strings** for all 3 IoT Devices, starting with "HostName=", are displayed. Copy all three of these connection strings into a text document, and save for later reference.
