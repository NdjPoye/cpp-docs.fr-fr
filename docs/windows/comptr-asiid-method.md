---
title: "ComPtr::AsIID, m&#233;thode | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::AsIID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsIID (méthode)"
ms.assetid: d5a3cdb2-796d-4410-966a-847c0e8fb226
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::AsIID, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Retourne un objet ComPtr représentant l'interface identifiée par l'ID d'interface spécifié.  
  
## Syntaxe  
  
```  
WRL_NOTHROW HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IUnknown>* p  
) const;  
```  
  
#### Paramètres  
 `riid`  
 Un ID d'interface.  
  
 `p`  
 Si pris en charge, un pointeur d'indirection double vers l'interface spécifiée par le paramètre `riid`; sinon, un pointeur vers IUnknown.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, un HRESULT indiquant l'erreur.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ComPtr, classe](../windows/comptr-class.md)