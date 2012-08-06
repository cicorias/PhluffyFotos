## PhluffyFotos Sample

PhluffyFotos is a Web 2.0 Picture Gallery Service where users can upload their pictures from the web or mobile device. Users can upload, tag, and share photos in this sample.

The sample utilizes several technologies including [ASP.NET MVC 4](http://www.asp.net/mvc/mvc4), [SQL Azure](http://www.windowsazure.com/en-us/home/features/sql-azure/) and [Windows Azure Storage](http://www.windowsazure.com/en-us/home/features/storage/), including Tables, Blobs, and Queues. In this sample, you will see how to pull together both a web applicatin and Windows Azure Worker role to build cloud applications. 

### Prerequisites

* [Visual Studio 2010](http://www.microsoft.com/visualstudio/en-us/products) with Service Pack 1 and SQL Express
* [Windows Azure SDK for .NET 1.6](http://www.windowsazure.com/en-us/develop/net/)
* [ASP.NET MVC 4 Beta](http://go.microsoft.com/fwlink/?LinkId=243392)

### Running the Sample Locally

1. Open Visual Studio 2010 as administrator.
2. Compile the solution. The NuGet packages dependencies will be automatically downloaded and installed.
2. Run the **PhluffyFotos** cloud project (right-click the project and select Debug | Start new Instance).
3. Run the **PhluffyFotos.Web** project (right-click the project and select Debug | Start new Instance).

### Running the Sample in Windows Azure

1. To run this sample on the cloud you need a Windows Azure Subscription. If you don't have a Windows Azure account, you can sign up for a free trial [here](http://www.windowsazure.com/en-us/pricing/free-trial/).

2. You also need a Windows Azure Storage account, for leveraging Queues, Table and Blob Storage. Once you have your Windows Azure subscription, follow the steps in [this article](http://msdn.microsoft.com/en-us/library/windowsazure/gg433066.aspx) to create a storage account. Make note of the account name and Primary Acess Key.

3. To update the solution with the values obtained previously, follow these steps:
	1. Start Visual Studio. 
	2. Open the **ServiceConfiguration.Cloud.cscfg** file located in the **PhluffyFotos** Cloud project.
	3. Modify the **DataConnectionsString** and the Diagnostic Connection string (Microsoft.WindowsAzure.Plugins.Diagnostics.ConnectionString) for the worker role to point to the storage account you've just created.
	
		> **Note:** The connection string used for accessing the windows azure storage account is built with the following format: `DefaultEndpointsProtocol=https;AccountName={yourservice};AccountKey={yourkey}`
		> In it you'll need to replace `{yourservice}` with the storage account name and `{yourkey}` with the Primary Access Key copied.

	4. Open the **Web.config** file located in the **PhluffyFotos.Web** project and update the **DataConnectionString** with the same value used in the step above.
	5. Save the changes made to the file.

4. Now create a SQL Azure database and update the **DataConnectionString** in **Web.config** from **PhluffyFotos.Web** project.

//TBC