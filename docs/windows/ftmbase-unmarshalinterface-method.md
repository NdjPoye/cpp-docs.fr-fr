---
title: "FtmBase::UnmarshalInterface, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase::UnmarshalInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UnmarshalInterface (méthode)"
ms.assetid: 6850a621-e9a6-4001-bc1e-bd5d1b121adc
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# FtmBase::UnmarshalInterface, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialise un proxy nouvellement créé et retourne un pointeur d'interface vers ce proxy.  
  
## Syntaxe  
  
```  
STDMETHODIMP UnmarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __deref_out void **ppv  
) override;  
```  
  
#### Paramètres  
 `pStm`  
 Pointeur vers le flux de données à partir duquel le pointeur d'interface doit être démarshalé.  
  
 `riid`  
 Référence à l'identificateur de l'interface à démarshaler.  
  
 `ppv`  
 Lorsque cette opération se termine, l'adresse d'une variable de pointeur qui accepte le pointeur d'interface demandé dans `riid`.  Si cette opération est réussie, \*`ppv` contient le pointeur d'interface demandé de l'interface à démarshaler.  
  
## Valeur de retour  
 S\_OK si l'opération a réussi; sinon, E\_NOINTERFACE ou E\_FAIL.  
  
## Configuration requise  
 **En\-tête:** ftm.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [FtmBase, classe](../windows/ftmbase-class.md)