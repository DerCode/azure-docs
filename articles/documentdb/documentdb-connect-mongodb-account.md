---
title: MongoDB connection string for DocumentDB account | Microsoft Docs
description: Learn how to connect your MongoDB app to an Azure DocumentDB account using a MongoDB connection string.
keywords: mongodb connection string
services: documentdb
author: AndrewHoh
manager: jhubbard
editor: ''
documentationcenter: ''

ms.assetid: e36f7375-9329-403b-afd1-4ab49894f75e
ms.service: documentdb
ms.workload: data-services
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 01/09/2016
ms.author: anhoh

---

# Connect a MongoDB app to a DocumentDB account using a MongoDB connection string
Learn how to connect your MongoDB app to an Azure DocumentDB account using a MongoDB connection string. By connecting your MongoDB app to an Azure DocumentDB database, you can use a DocumentDB database as the data store for your MongoDB app. 

This tutorial provides two ways to retrieve connection string information:

- [The Quick start method](#QuickStartConnection), for use with .NET, Node.js, MongoDB Shell, Java, and Python drivers.
- [The custom connection string method](#GetCustomConnection), for use with other drivers.

## Prerequisites

- An Azure account. If you don't have an Azure account, create a [free Azure account](https://azure.microsoft.com/free/) now. 
- A DocumentDB account. For instructions, see [Create a DocumentDB account for use with MongoDB apps](documentdb-create-mongodb-account.md).

## <a id="QuickStartConnection"></a>Get the MongoDB connection string using the Quick start
1. In an internet browser, sign in to the [Azure Portal](https://portal.azure.com).
2. In the **NoSQL (DocumentDB)** blade, select the DocumentDB account with protocol support for MongoDB. 
3. In the **Left Navigation** bar of the account blade, click **Quick start**. 
4. Choose your platform (*.NET driver*, *Node.js driver*, *MongoDB Shell*, *Java driver*, *Python driver*). If you don't see your driver or tool listed, don't worry, we continuously document more connection code snippets. Please comment below on what you'd like to see and read [Get the account's connection string information](#GetCustomConnection) to learn how to craft your own connection.
5. Copy and paste the code snippet into your MongoDB app, and you are ready to go.

    ![Screen shot of the quick start blade](./media/documentdb-connect-mongodb-account/QuickStartBlade.png)

## <a id="GetCustomConnection"></a> Get the MongoDB connection string to customize
1. In an internet browser, sign in to the [Azure Portal](https://portal.azure.com).
2. In the **NoSQL (DocumentDB)** blade, select the DocumentDB account with protocol support for MongoDB. 
3. In the **Left Navigation** bar of the account blade, click **Connection String**. 
4. The **Connection String Information** blade opens and has all the information necessary to connect to the account using a driver for MongoDB, including a pre-constructed connection string.

    ![Screen shot of the connection string blade](./media/documentdb-connect-mongodb-account/ConnectionStringBlade.png)

## Connection string requirements
> [!Important]
> DocumentDB has strict security requirements and standards. DocumentDB accounts require authentication and secure communication via **SSL**.
>
>

It is important to note that DocumentDB supports the standard MongoDB connection string URI format, with a couple of specific requirements: DocumentDB accounts require authentication and secure communication via SSL.  Thus, the connection string format is:

    mongodb://username:password@host:port/[database]?ssl=true

Where the values of this string are available in the Connection String blade shown above.

* Username (required)
  * DocumentDB account name
* Password (required)
  * DocumentDB account password
* Host (required)
  * FQDN of DocumentDB account
* Port (required)
  * 10250
* Database (optional)
  * The default database used by the connection (if no database is provided, the default database is "test")
* ssl=true (required)

For example, consider the account shown in the Connection String Information above.  A valid connection string is:

    mongodb://contoso123:0Fc3IolnL12312asdfawejunASDF@asdfYXX2t8a97kghVcUzcDv98hawelufhawefafnoQRGwNj2nMPL1Y9qsIr9Srdw==@anhohmongo.documents.azure.com:10250/mydatabase?ssl=true

## Next steps
* Learn how to [use MongoChef](documentdb-mongodb-mongochef.md) with a DocumentDB account with protocol support for MongoDB.
* Explore DocumentDB with protocol support for MongoDB [samples](documentdb-mongodb-samples.md).
