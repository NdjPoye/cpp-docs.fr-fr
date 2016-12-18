---
title: "FtmBase::MarshalInterface, m&#233;thode | Microsoft Docs"
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
  - "ftm/Microsoft::WRL::FtmBase::MarshalInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MarshalInterface (méthode)"
ms.assetid: fc8421b4-06e4-4925-b908-c285fe4790d2
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# FtmBase::MarshalInterface, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Écrit dans un flux les données requises pour initialiser un objet proxy dans un processus client.  
  
## Syntaxe  
  
```  
STDMETHODIMP MarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags  
) override;  
```  
  
#### Paramètres  
 `pStm`  
 Pointeur vers le flux de données à utiliser lors du marshaling.  
  
 `riid`  
 Référence à l'identificateur de l'interface à marshaler.  Cette interface doit être dérivée de l'interface IUnknown.  
  
 `pv`  
 Pointeur vers un pointeur d'interface à marshaler; peut être NULL si l'appelant ne possède pas de pointeur vers l'interface souhaitée.  
  
 `dwDestContext`  
 Contexte de destination où l'interface spécifiée doit être démarshalée.  
  
 Spécifiez une ou plusieurs valeurs d'énumération de MSHCTX.  
  
 La démarshalisation peut se produire dans un autre appartement du processus actuel \(MSHCTX\_INPROC\) ou dans un autre processus sur le même ordinateur que le processus actuel \(MSHCTX\_LOCAL\).  
  
 `pvDestContext`  
 Réservé pour une future utilisation ; doit être nul.  
  
 `mshlflags`  
 Spécifie si les données à marshaler doivent être transmises au processus client, le cas courant, ou être écrites dans un tableau global, où elles peuvent être récupérées par plusieurs clients.  
  
## Valeur de retour  
 S\_OK  
 Le pointeur d'interface a été marshalé avec succès.  
  
 E\_NOINTERFACE  
 L'interface spécifiée n'est pas prise en charge.  
  
 STG\_E\_MEDIUMFULL  
 Le flux est plein.  
  
 E\_FAIL  
 Échec de l'opération.  
  
## Configuration requise  
 **En\-tête:** ftm.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [FtmBase, classe](../windows/ftmbase-class.md)