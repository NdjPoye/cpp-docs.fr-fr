---
title: "ComPtr::operator-&gt;, op&#233;rateur | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr::operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "-> (opérateur)"
ms.assetid: 7b7faefd-d1e4-4f31-a77d-17a42e0d6b6a
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator-&gt;, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Récupère un pointeur vers le type spécifié par le paramètre de modèle actuel.  
  
## Syntaxe  
  
```  
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;  
```  
  
## Valeur de retour  
 Pointeur vers le type spécifié par le nom du type de modèle actuel.  
  
## Remarques  
 Cette fonction d'assistance supprime la charge mémoire inutile provoquée par l'utilisation de la macro STDMETHOD.  Cette fonction produit des types IUnknown privés au lieu de virtuel.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [ComPtr, classe](../windows/comptr-class.md)