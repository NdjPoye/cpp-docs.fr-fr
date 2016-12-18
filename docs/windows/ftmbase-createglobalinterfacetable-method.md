---
title: "FtmBase::CreateGlobalInterfaceTable, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateGlobalInterfaceTable (méthode)"
ms.assetid: bb82a0c5-22b9-4844-9204-7922033d8b07
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# FtmBase::CreateGlobalInterfaceTable, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Crée un tableau global d'interface \(GIT\).  
  
## Syntaxe  
  
```  
static HRESULT CreateGlobalInterfaceTable(  
   __out IGlobalInterfaceTable **git  
);  
```  
  
#### Paramètres  
 `git`  
 Lorsque cette opération se termine, un pointeur vers un tableau global d'interface.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, un HRESULT indiquant l'erreur.  
  
## Remarques  
 Pour plus d'informations, consultez la rubrique « IGlobalInterfaceTable » dans la sous\-rubrique « Interfaces COM » de la rubrique « Référence COM » dans la bibliothèque MSDN.  
  
## Configuration requise  
 **En\-tête:** ftm.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [FtmBase, classe](../windows/ftmbase-class.md)