## PhluffyFotos Sample

PhluffyFotos is a Picture Gallery Service where users can upload their pictures from the web or mobile device. Users can upload, tag, and share photos in this sample.

The sample utilizes several technologies including [ASP.NET MVC 4](http://www.asp.net/mvc/mvc4), [Windows Azure SQL Databases](http://www.windowsazure.com/en-us/develop/net/how-to-guides/sql-database/) and [Windows Azure Storage](http://www.windowsazure.com/en-us/home/features/storage/), including [Tables](https://www.windowsazure.com/en-us/develop/net/how-to-guides/table-services/), [Blobs](https://www.windowsazure.com/en-us/develop/net/how-to-guides/blob-storage/), and [Queues](https://www.windowsazure.com/en-us/develop/net/how-to-guides/queue-service/). In this sample, you will see how to pull together both a web application and Windows Azure Worker role to build cloud applications. 

### Prerequisites

* [Visual Studio 2012](http://www.microsoft.com/visualstudio/en-us/products) 
* [Windows Azure SDK for .NET 1.7](http://www.windowsazure.com/en-us/develop/net/)
* [ASP.NET MVC 4](http://www.asp.net/mvc/mvc4)

### Running the Sample Locally

1. Open Visual Studio 2012 as administrator.
2. Compile the solution. The NuGet packages dependencies will be automatically downloaded and installed.
2. Run the **PhluffyFotos** cloud project (right-click the project and select Debug | Start new Instance).
3. Run the **PhluffyFotos.Web** project (right-click the project and select Debug | Start new Instance).

### Running the Sample in Windows Azure

1. To run this sample on the cloud you need a Windows Azure Subscription. If you don't have a Windows Azure account, you can sign up for a free trial [here](http://bit.ly/windowsazuretrial).

2. You also need a Windows Azure Storage account, for leveraging Queues, Table and Blob Storage. Once you have your Windows Azure subscription, follow the steps in [this article](https://www.windowsazure.com/en-us/develop/net/how-to-guides/blob-storage/) to create a storage account. Make note of the account name and Primary Acess Key.

3. To update the solution with the values obtained previously, follow these steps:
	1. Use the Windows Azure portal to create a Web site with a database
	1. Use the Windows Azure portal to create a Cloud Service
	1. Use the Windows Azure portal to create a Windows Azure Storage account
	1. Start Visual Studio 2012 and open the solution included with this sample's download.
	1. Open the **ServiceConfiguration.Cloud.cscfg** file located in the **PhluffyFotos** Cloud project.
	1. Modify the **DataConnectionsString** and the Diagnostic Connection string (Microsoft.WindowsAzure.Plugins.Diagnostics.ConnectionString) for the worker role to point to the storage account you've just created.

		> **Note:** The connection string used for accessing the windows azure storage account is built with the following format: `DefaultEndpointsProtocol=https;AccountName={YOUR-ACCONT};AccountKey={YOUR-ACCONT-KEY}`
		> In it you'll need to replace `{YOUR-ACCONT}` with the storage account name and `{YOUR-ACCONT-KEY}` with the Primary Access Key copied.
	1. Open the **Web.config** file located in the **PhluffyFotos.Web** project and update the **DataConnectionString** with the same value used in the step above.
	1. Open the **Web.config** file located in the **PhluffyFotos.Web** project and update the **DefaultConnection** connction string to reflect the connection string to the Windows Azure SQL Database you created in step 1.
	1. Save the changes made to the file.

4. Publish the **PhlufffyPhotos** Cloud Service project to the Windows Azure Cloud Service you created in Step 2.
5. Publish the **PhluffuPhotos.Web** project to the Windows Azure Web Site you created in Step 1.

### Detailed Instructions ###
For a more detailed walk-through on how to perform each of the individual tasks required to get this sample working in Windows Azure, see the sample's [Getting Started document](https://github.com/WindowsAzure-Samples/PhluffyFotos/blob/master/GettingStarted.md) in the repository containing the code for the sample. 