---
title: "FtmBase::DisconnectObject, m&#233;thode | Microsoft Docs"
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
  - "ftm/Microsoft::WRL::FtmBase::DisconnectObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DisconnectObject (méthode)"
ms.assetid: 33253eec-3a65-4e72-8525-0249245a4790
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# FtmBase::DisconnectObject, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Libère de force toutes les connexions externes à un objet.  Le serveur de l'objet appelle l'implémentation de l'objet de cette méthode avant de s'arrêter.  
  
## Syntaxe  
  
```  
STDMETHODIMP DisconnectObject(  
   __in DWORD dwReserved  
) override;  
```  
  
#### Paramètres  
 `dwReserved`  
 Réservé pour une future utilisation ; doit être nul.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, un HRESULT indiquant l'erreur.  
  
## Configuration requise  
 **En\-tête:** ftm.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [FtmBase, classe](../windows/ftmbase-class.md)