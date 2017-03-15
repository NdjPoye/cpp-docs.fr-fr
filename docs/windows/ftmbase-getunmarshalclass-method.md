---
title: "FtmBase::GetUnmarshalClass, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetUnmarshalClass (méthode)"
ms.assetid: 535fc539-5b97-4967-b158-f7568f13d341
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# FtmBase::GetUnmarshalClass, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient le CLSID que COM utilise pour localiser la DLL contenant le code du proxy correspondant.  COM charge cette DLL pour créer une instance non initialisée du proxy.  
  
## Syntaxe  
  
```  
STDMETHODIMP GetUnmarshalClass(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out CLSID *pCid  
) override;  
```  
  
#### Paramètres  
 `riid`  
 Référence à l'identificateur de l'interface à marshaler.  
  
 `pv`  
 Pointeur vers l'interface à marshaler; peut être NULL si l'appelant ne possède pas de pointeur vers l'interface souhaitée.  
  
 `dwDestContext`  
 Contexte de destination où l'interface spécifiée doit être démarshalée.  
  
 Spécifiez une ou plusieurs valeurs d'énumération de MSHCTX.  
  
 La démarshalisation peut se produire soit dans un autre appartement du processus actuel \(MSHCTX\_INPROC\), soit dans un autre processus sur le même ordinateur que le processus actuel \(MSHCTX\_LOCAL\).  
  
 `pvDestContext`  
 Réservé à une utilisation ultérieure; doit être NULL.  
  
 `mshlflags`  
 Lorsque cette opération se termine, le pointeur vers le CLSID à utiliser pour créer un proxy dans le processus client.  
  
 `pCid`  
  
## Valeur de retour  
 Retourne S\_OK si l'opération a réussi; sinon S\_FALSE.  
  
## Configuration requise  
 **En\-tête:** ftm.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [FtmBase, classe](../windows/ftmbase-class.md)