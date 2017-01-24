---
title: "CDataConnection::Open | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataConnection.Open"
  - "ATL.CDataConnection.Open"
  - "CDataConnection::Open"
  - "ATL::CDataConnection::Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open (méthode)"
ms.assetid: 2c6f0c01-4954-43ba-973e-861ac8e82892
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Établit une connexion à une source de données à l'aide d'une chaîne d'initialisation.  
  
## Syntaxe  
  
```  
  
      HRESULT Open(   
   LPCOLESTR szInitString    
) throw( );  
```  
  
#### Paramètres  
 *szInitString*  
 \[in\] La chaîne d'initialisation pour la source de données.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDataConnection, classe](../../data/oledb/cdataconnection-class.md)