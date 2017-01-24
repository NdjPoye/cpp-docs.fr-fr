---
title: "InterfaceTraits::CanCastTo, m&#233;thode | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::InterfaceTraits::CanCastTo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanCastTo (méthode)"
ms.assetid: 275847cb-69ea-42bf-910f-05ba6ef8b48d
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# InterfaceTraits::CanCastTo, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
  
template<typename T>  
static __forceinline bool CanCastTo(  
   _In_ T* ptr,  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
  
```  
  
#### Paramètres  
 `ptr`  
 Le nom d'un pointeur vers un type.  
  
 `riid`  
 L'id de l'interface de `Base`.  
  
 `ppv`  
 Si cette opération est réussie, `ppv` pointe vers l'interface spécifiée par `Base`.  Sinon, `ppv` est défini à `nullptr`.  
  
## Valeur de retour  
 `true` si cette opération réussit et `ptr` est casté en un pointeur vers `Base`; sinon, `false` .  
  
## Remarques  
 Indique si le pointeur spécifié peut être casté en un pointeur vers `Base`.  
  
 Pour plus d'informations sur `Base`, consultez la section Typedefs Publiques dans [InterfaceTraits, structure](../windows/interfacetraits-structure.md).  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [InterfaceTraits, structure](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)