This tool is for setting up the CSI Connect either via USB or over cloud.

For internal use and testing only.
This is a work in progress, bugs and crashes can therefore happen.
If you notice any bugs/crashes, please write a description of how to reproduce the bug/crash and send it to: emils.christiansen@hydac.dk

For optimal experience only use this tool with CSI Connect devices with firmware version 6. and newer.

For setup via Cloud please note:
	- The device must be online (Cloud-LED breathing cyan).
	- If first time setup of device, make sure it is not claimed to another account.
	- You should sign into an account in the tool or if you do not have one create one using the tool.
The process:
	- Wait for device to connect to the cloud (Cloud-LED breathing cyan).
	- Sign in to or create your account from the "Overview" tab.
	- Click the "Find Device Online" button and wait for the window to open.
	- A list should appear that contains all devices claimed to your account that is online.
		- If the list is empty that means you either do not have any claimed devices, or that your devices are not online.
		- For first time setup of a device click the "Add device" button and enter the "name" of the device, unless otherwise notified, the name will be the serial number printed on the device.
		- It is also possible to unclaim or rename already claimed devices.
	- Select a device from the list by clicking on it and click "OK".
	- The dialog should close and the Fields in "Device Info" should update with information on the selected device. The selector in the bottom left should also have updated to say "Cloud" indicating that you are "Connected" to a device via cloud.
	- From here you can click the "Fetch From Device" button to get information from the device. or you can change to different tabs containing settings. When changing tabs, the new tab will update the information from the device.
	- Note that fetching settings from the device takes some time and the program may become unresponsive for a while.
	- On the settings tabs, when the wanted settings on a specific tab have been entered, click the "Save To Device" button and wait. As with reading from the device this takes a while, for some settings it can take up to a minute to save the settings.
	
Setting up webhooks for a device:
	- You need to be signed in.
	- The device must be claimed to your account.
	- The device must be online (Cloud-LED breathing cyan).
The process:
	- After setting the desired sensors and data stream settings for the device, go to the "Web Hook" tab (Only accessible if signed in).
	- A list will show all existing integrations for the selected device. If none exist, the list will be empty.
	- Clicking on an existing webhook will load it in the bottom tab view, where it can be edited.
	- A new webhook is created by filling in the information in the bottom tab view. 
	
	- There are three ways to set up a webhook, "CMX Integration", "Custom Web Hook" and "Advanced”.
		- CMX integration is an easy way to set up a webhook that sends data to CMX.
			- Enter the URL for your CMX server
			- Enter you CMX username and password
			- Enter Id Channel Id and Datapoint id for the used sensor channels. To the top right the structure of the data sent from the device is shown, this is the data the web hook can pass on.
		- Custom Web Hook is a middle of the road way the set up an integration for different endpoints.
			- Enter the URL the data is to be sent to.
			- Choose what request type the webhook is to send to the URL from the dropdown.
			- Chose weather the data is to be a custom string or a JSON, for more information on what to chose and how to write the web hook body click the documentation.
			- Enter the wanted data being sent. To the top right the structure of the data sent from the device is shown, this is the data the web hook can pass on.
		- Advanced is a way to create a web hook with almost unlimited freedom.
			- The webhook is made based on the entered JSON, the fields  "deviceID", "event", "url" and "requestType" must be in the JSON.
			- "event" must be set to "dataEvent".
			- For more information click the "Documentation" button, this will take you to particle.io documentation on web hooks.
	
	- When all data has been entered, click the "Create New" button to create a new web hook, or the "Edit Selected" button to update settings of a existing web hook.
	
	- Web hooks can also be deleted from here.


For setup using USB please note:
	- The USB port is not accessible without opening the enclosure using tools, it is only intended for debugging and internal testing.
	- The device must be online (Cloud-LED breathing cyan).
	- It is possible to change settings for all devices no matter who has claimed it.
	- You do not need to sign in, but you can if you want to set up webhooks. (For setting up webhooks the device must be claimed to you.
The process:
	- Wait for device to connect to the cloud (Cloud-LED breathing cyan).
	- If you want you can sign in.
	- Connect the device USB Port (You need to open the enclosure to access)
	- Click the "Update Connections" button, the selector should then show one or more COM Ports, depending of the number of CSI Connect devices connected.
	- Select a COM Device from the selector, only CSI Connect devices will show up. 
	- The tool now behaves like when using it via cloud, except most communication to the device will be much faster, although saving settings to the device can still take up to 30 seconds, and the program might seem unresponsive. 











