---
title: "_com_ptr_t::QueryInterface | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::QueryInterface"
  - "_com_ptr_t.QueryInterface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "QueryInterface (méthode)"
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t::QueryInterface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Appelle la fonction membre `QueryInterface` de **IUnknown** sur le pointeur d'interface encapsulé.  
  
## Syntaxe  
  
```  
  
      template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType*& p   
) throw ( );  
template<typename _InterfaceType> HRESULT QueryInterface (  
   const IID& iid,  
   _InterfaceType** p  
) throw( );  
```  
  
#### Paramètres  
 `iid`  
 **IID** d'un pointeur d'interface.  
  
 `p`  
 Pointeur d'interface brut.  
  
## Notes  
 Appelle **IUnknown::QueryInterface** sur le pointeur d'interface encapsulé avec l'**IID** spécifié et retourne le pointeur d'interface brut résultant dans `p`.  Cette routine retourne l'objet `HRESULT` pour indiquer un succès ou un échec.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_ptr\_t, classe](../cpp/com-ptr-t-class.md)