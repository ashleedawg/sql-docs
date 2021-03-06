---
title: "Run Windows PowerShell Steps in SQL Server Agent | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: sql
ms.prod_service: "powershell"
ms.service: ""
ms.component: "powershell"
ms.reviewer: ""
ms.suite: "sql"
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f25f7549-c9b3-4618-85f2-c9a08adbe0e3
caps.latest.revision: 10
author: "stevestein"
ms.author: "sstein"
manager: "craigg"
---
# Run Windows PowerShell Steps in SQL Server Agent
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

Use SQL Server Agent to run SQL Server PowerShell scripts at schedule times.  
  
**To run PowerShell from SQL Server Agent, using:**  [PowerShell Job Step](#PShellJob), [Command Prompt Job Step](#CmdExecJob)  
  
> [!NOTE]
> There are two SQL Server PowerShell modules; **SqlServer** and **SQLPS**. The **SQLPS** module is included with the SQL Server installation (for backwards compatibility), but is no longer being updated. The most up-to-date PowerShell module is the **SqlServer** module. The **SqlServer** module contains updated versions of the cmdlets in **SQLPS**, and also includes new cmdlets to support the latest SQL features.  
> Previous versions of the **SqlServer** module *were* included with SQL Server Management Studio (SSMS), but only with the 16.x versions of SSMS. To use PowerShell with SSMS 17.0 and later, the **SqlServer** module must be installed from the PowerShell Gallery.
> To install the **SqlServer** module, see [Install SQL Server PowerShell](download-sql-server-ps-module.md).


There are several types of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job steps. Each type is associated with a subsystem that implements a specific environment, such as a replication agent or command prompt environment. You can code Windows PowerShell scripts, and then use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent to include the scripts in jobs that run at scheduled times or in response to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] events. Windows PowerShell scripts can be run using either a command prompt job step or a PowerShell job step.  
  
1.  Use a PowerShell job step to have the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent subsystem run the **sqlps** utility, which launches PowerShell and imports the **sqlps** module.  
  
2.  Use a command prompt job step to run PowerShell.exe, and specify a script that imports the **sqlps** module.  
  
###  <a name="LimitationsRestrictions"></a> Limitations and Restrictions  
  
> [!CAUTION]  
>  Each [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent job step that runs PowerShell with the **sqlps** module launches a process, which consumes approximately 20 MB of memory. Running large numbers of concurrent Windows PowerShell job steps can adversely impact performance.  
  
##  <a name="PShellJob"></a> Create a PowerShell Job Step  
 **To create a PowerShell job step**  
  
1.  Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**. For more information about creating a job, see [Creating Jobs](http://msdn.microsoft.com/library/465fb7fc-7622-4252-a178-ea51691c935b).  
  
2.  In the **Job Properties** dialog, click the **Steps** page, and then click **New**.  
  
3.  In the **New Job Step** dialog, type a job **Step name**.  
  
4.  In the **Type** list, click **PowerShell**.  
  
5.  In the **Run as** list, select the proxy account with the credentials that the job will use.  
  
6.  In the **Command** box, enter the PowerShell script syntax that will be executed for the job step. Alternately, click **Open** and select a file containing the script syntax.  
  
7.  Click the **Advanced** page to set the following job step options: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should try to execute the job step, and how often retry attempts should be made.  
  
##  <a name="CmdExecJob"></a> Create a Command Prompt Job Step  
 **To create a CmdExec job step**  
  
1.  Expand **SQL Server Agent**, create a new job or right-click an existing job, and then click **Properties**. For more information about creating a job, see [Creating Jobs](http://msdn.microsoft.com/library/465fb7fc-7622-4252-a178-ea51691c935b).  
  
2.  In the **Job Properties** dialog, click the **Steps** page, and then click **New**.  
  
3.  In the **New Job Step** dialog, type a job **Step name**.  
  
4.  In the **Type** list, choose **Operating system (CmdExec)**.  
  
5.  In **Run as** list, select the proxy account with the credentials that the job will use. By default, CmdExec job steps run under the context of the SQL Server Agent service account.  
  
6.  In the **Process exit code of a successful command** box, enter a value from 0 to 999999.  
  
7.  In the **Command** box, enter powershell.exe with parameters specifying the PowerShell script to be run.  
  
8.  Click the **Advanced** page to set job step options, such as: what action to take if the job step succeeds or fails, how many times [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should try to execute the job step, and the file where [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent can write the job step output. Only members of the **sysadmin** fixed server role can write job step output to an operating system file.  
  
## See Also  
 [SQL Server PowerShell](sql-server-powershell.md)  
  
  
