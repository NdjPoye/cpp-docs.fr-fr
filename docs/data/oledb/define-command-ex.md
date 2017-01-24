---
title: "DEFINE_COMMAND_EX | Microsoft Docs"
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
  - "DEFINE_COMMAND_EX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DEFINE_COMMAND_EX (macro)"
ms.assetid: d3e2ef20-1455-46d2-8499-8ab84bbb90a4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DEFINE_COMMAND_EX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie la commande qui sera utilisée pour créer l'ensemble des lignes lorsque vous utilisez la classe [CCommand](../../data/oledb/ccommand-class.md).  Prend en charge Unicode et les applications ANSI.  
  
## Syntaxe  
  
```  
  
DEFINE_COMMAND_EX(  
x  
,   
wszCommand  
 )  
  
```  
  
#### Paramètres  
 *x*  
 \[in\] Le nom de la classe d'enregistrement d'utilisateur \(commande\).  
  
 `wszCommand`  
 \[in\] la chaîne de commande qui sera utilisée pour créer l'ensemble des lignes lorsque vous utilisez [CCommand](../../data/oledb/ccommand-class.md).  
  
## Notes  
 La chaîne de commande que vous spécifiez sera utilisée par défaut si vous ne spécifiez pas le texte de commande dans la méthode [CCommand::Open](../../data/oledb/ccommand-open.md).  
  
 La macro accepte les chaînes Unicode, quel que soit le type d'application.  La macro est préférable sur [DEFINE\_COMMAND](../../data/oledb/define-command.md) car elle prend en charge Unicode ainsi que des applications ANSI.  
  
## Exemple  
 Voir le [BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)