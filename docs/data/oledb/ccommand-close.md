---
title: "CCommand::Close | Microsoft Docs"
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
  - "CCommand.Close"
  - "CCommand::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close (méthode)"
ms.assetid: 4da9c02c-7082-4e47-a0fa-78b546f0f7d2
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCommand::Close
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Libère l'ensemble de lignes accesseur associé à la commande.  
  
## Syntaxe  
  
```  
void Close( );  
```  
  
## Notes  
 Une commande utilise un ensemble de lignes, un accesseur de l'ensemble de résultats, et \(éventuellement\) un accesseur de paramètre \(contrairement aux tables, qui ne prennent pas en charge les paramètres et n'ont pas besoin d'un accesseur de paramètre\).  
  
 Lorsque vous exécutez une commande, vous devez appeler `Close` et [ReleaseCommand](../../data/oledb/ccommand-releasecommand.md) après la commande.  
  
 Lorsque vous souhaitez exécuter le même ordre à plusieurs reprises, vous devez libérer chaque accesseur de l'ensemble de résultats en appelant `Close` avant d'appeler `Execute`.  À la fin de la série, vous devez libérer un accesseur de paramètre en appelant `ReleaseCommand`.  Un autre scénario courant appelle une procédure stockée qui possède des paramètres de sortie.  Dans de nombreux fournisseurs \(tels que le fournisseur OLE DB pour SQL Server\), les valeurs de paramètres de sortie ne sont pas accessibles jusqu'à ce que vous fermiez l'accesseur de l'ensemble de résultats.  Appelez `Close` pour fermer les accesseurs retourné d'ensemble de lignes et de jeu de résultats, mais pas l'accesseur de paramètre, ce qui vous permet de récupérer les valeurs des paramètres de sortie.  
  
## Exemple  
 L'exemple suivant montre comment appeler `Close` et `ReleaseCommand` lorsque vous exécutez la même commande de façon répétée.  
  
 [!code-cpp[NVC_OLEDB_Consumer#2](../../data/oledb/codesnippet/CPP/ccommand-close_1.cpp)]  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CCommand, classe](../../data/oledb/ccommand-class.md)   
 [CCommand::ReleaseCommand](../../data/oledb/ccommand-releasecommand.md)