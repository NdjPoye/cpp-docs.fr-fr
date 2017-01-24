---
title: "Debugging and Error Reporting Global Functions | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fonctions (ATL), rapport d'erreurs"
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
caps.latest.revision: 17
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Debugging and Error Reporting Global Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ces fonctions permettent le débogage utiles et suivent des fonctionnalités.  
  
|||  
|-|-|  
|[AtlHresultFromLastError](../Topic/AtlHresultFromLastError.md)|Retourne un code d'erreur d' `GetLastError` sous la forme d'un HRESULT.|  
|[AtlHresultFromWin32](../Topic/AtlHresultFromWin32.md)|Convertit un code d'erreur Win32 dans un HRESULT.|  
|[AtlReportError](../Topic/AtlReportError.md)|Installation **IErrorInfo** pour fournir des informations d'erreur à un client.|  
|[AtlThrow](../Topic/AtlThrow.md)|Lève `CAtlException`.|  
|[AtlThrowLastWin32](../Topic/AtlThrowLastWin32.md)|Appelez cette fonction pour signaler une erreur en fonction de le résultat de la fonction Windows `GetLastError`.|  
|[AtlTraceLoadSettings](../../misc/atltraceloadsettings.md)|Appelez cette fonction pour charger des paramètres de trace à partir d'un fichier.|  
|[AtlTraceSaveSettings](../../misc/atltracesavesettings.md)|Appelez cette fonction pour enregistrer les paramètres de trace dans un fichier.|  
  
## Voir aussi  
 [Fonctions](../../atl/reference/atl-functions.md)   
 [Debugging and Error Reporting Macros](../../atl/reference/debugging-and-error-reporting-macros.md)