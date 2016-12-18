---
title: "DEFINE_COMMAND | Microsoft Docs"
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
  - "DEFINE_COMMAND"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DEFINE_COMMAND (macro)"
ms.assetid: 9d724968-e242-413c-9a13-e7175fccf9b1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DEFINE_COMMAND
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie la commande qui sera utilisée pour créer l'ensemble des lignes lorsque vous utilisez la classe [CCommand](../../data/oledb/ccommand-class.md).  Accepte uniquement les types chaîne correspondant au type d'application spécifié \(ANSI ou Unicode\).  
  
> [!NOTE]
>  Il est recommandé d'utiliser [DEFINE\_COMMAND\_EX](../../data/oledb/define-command-ex.md) au lieu de `DEFINE_COMMAND`.  
  
## Syntaxe  
  
```  
  
DEFINE_COMMAND(  
x  
,   
szCommand  
 )  
  
```  
  
#### Paramètres  
 *x*  
 \[in\] Le nom de la classe d'enregistrement d'utilisateur \(commande\).  
  
 `szCommand`  
 \[in\] la chaîne de commande qui sera utilisée pour créer l'ensemble des lignes lorsque vous utilisez [CCommand](../../data/oledb/ccommand-class.md).  
  
## Notes  
 La chaîne de commande que vous spécifiez sera utilisée par défaut si vous ne spécifiez pas le texte de commande dans la méthode [CCommand::Open](../../data/oledb/ccommand-open.md).  
  
 La macro accepte les chaînes ANSI si vous créez votre application comme ANSI ou des chaînes Unicode si vous créez votre application au format Unicode.  Il est recommandé d'utiliser [DEFINE\_COMMAND\_EX](../../data/oledb/define-command-ex.md) au lieu de `DEFINE_COMMAND`, car le précédent accepte les chaînes Unicode, quel que soit le type d'application ANSI ou Unicode.  
  
## Exemple  
 Voir le [BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)