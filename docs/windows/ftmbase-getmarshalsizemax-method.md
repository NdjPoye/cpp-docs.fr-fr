---
title: "FtmBase::GetMarshalSizeMax, m&#233;thode | Microsoft Docs"
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
  - "ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetMarshalSizeMax (méthode)"
ms.assetid: b416b1bf-c73e-45d5-abb8-04921c1a0c94
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# FtmBase::GetMarshalSizeMax, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient la limite supérieure du nombre d'octets nécéssaires pour marshaler le pointeur d'interface spécifié sur l'objet spécifié.  
  
## Syntaxe  
  
```  
STDMETHODIMP GetMarshalSizeMax(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out DWORD *pSize  
) override;  
```  
  
#### Paramètres  
 `riid`  
 Référence à l'identificateur de l'interface à marshaler.  
  
 `pv`  
 Pointeur d'interface devant être marshalé; peut être NULL.  
  
 `dwDestContext`  
 Contexte de destination où l'interface spécifiée doit être démarshalée.  
  
 Spécifiez une ou plusieurs valeurs d'énumération de MSHCTX.  
  
 Actuellement, la démarshalisation peut se produire soit dans un autre appartement du processus actuel \(MSHCTX\_INPROC\), soit dans un autre processus sur le même ordinateur que le processus actuel \(MSHCTX\_LOCAL\).  
  
 `pvDestContext`  
 Réservé à une utilisation ultérieure; doit être NULL.  
  
 `mshlflags`  
 Indicateur spécifiant si les données à marshaler doivent être transmises au processus client, le cas courant, ou être écrites dans un tableau global, où elles peuvent être récupérées par plusieurs clients.  Spécifie une ou plusieurs valeurs d'énumération de MSHLFLAGS.  
  
 `pSize`  
 Lorsque cette opération se termine, le pointeur vers la limite supérieure de la quantité de données à être écrite dans le flux de marshaling.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, E\_FAIL ou E\_NOINTERFACE.  
  
## Configuration requise  
 **En\-tête:** ftm.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [FtmBase, classe](../windows/ftmbase-class.md)