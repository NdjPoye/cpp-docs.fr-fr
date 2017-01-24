---
title: "CCommand::ReleaseCommand | Microsoft Docs"
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
  - "CCommand.ReleaseCommand"
  - "ReleaseCommand"
  - "CCommand::ReleaseCommand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseCommand (méthode)"
ms.assetid: 3b58230c-13d5-45c5-b43e-bb013ecc3019
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCommand::ReleaseCommand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Libère l'accesseur de paramètre, puis libère la commande elle\-même.  
  
## Syntaxe  
  
```  
  
void CCommandBase::ReleaseCommand( ) throw( );  
  
```  
  
## Notes  
 `ReleaseCommand` est utilisé en association avec **Close**.  Voir [Close](../../data/oledb/ccommand-close.md) pour plus d'informations sur l'utilisation.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CCommand, classe](../../data/oledb/ccommand-class.md)   
 [CCommand::Close](../../data/oledb/ccommand-close.md)