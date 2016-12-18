---
title: "ComPtr::ComPtr, constructeur | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::ComPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ComPtr, constructeur"
ms.assetid: eaf70907-beac-458f-a503-2e5e27b0c196
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::ComPtr, constructeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialise une nouvelle instance de la classe ComPtr.  Les surcharges fournissent un constructeur par défaut, un constructeur de copie, un constructeur de déplacement, ainsi qu'un constructeur de conversion.  
  
## Syntaxe  
  
```  
WRL_NOTHROW ComPtr();  
WRL_NOTHROW ComPtr(  
   decltype(__nullptr)  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr(  
   const ComPtr& other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   const ComPtr<U> &other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr &&other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr<U>&& other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
```  
  
#### Paramètres  
 `U`  
 Type du paramètre `other`.  
  
 `other`  
 Objet de type `U`.  
  
## Valeur de retour  
  
## Notes  
 Le premier constructeur est le constructeur par défaut, qui crée implicitement un objet vide.  Le deuxième constructeur spécifie [\_\_nullptr](../windows/nullptr-cpp-component-extensions.md), qui crée explicitement un objet vide.  
  
 Le troisième constructeur crée un objet à partir de l'objet spécifié par un pointeur.  
  
 Les quatrième et cinquième constructeurs sont des constructeurs de copie.  Le cinquième constructeur copie un objet s'il peut être converti au type actuel.  
  
 Les sixième et septième constructeurs sont des constructeurs de déplacement.  Le septième constructeur déplace un objet s'il peut être converti au type actuel.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ComPtr, classe](../windows/comptr-class.md)