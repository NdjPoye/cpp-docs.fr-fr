---
title: "IID_PPV_ARGS_Helper, fonction | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/IID_PPV_ARGS_Helper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IID_PPV_ARGS_Helper (fonction)"
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# IID_PPV_ARGS_Helper, fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vérifie que le type de l'argument spécifié dérive de l'interface `IUnknown`.  
  
> [!IMPORTANT]
>  Cette spécialisation de modèle prend en charge l'infrastructure WRL et n’est pas destinée à être utilisée directement à partir de votre code.  Utilisez plutôt [IID\_PPV\_ARGS](http://msdn.microsoft.com/library/windows/desktop/ee330727.aspx).  
  
## Syntaxe  
  
```  
template<  
   typename T  
>  
void** IID_PPV_ARGS_Helper(  
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp  
);  
```  
  
#### Paramètres  
 `T`  
 Le type de l'argument `pp`.  
  
 `pp`  
 Un pointeur double d'indirection.  
  
## Valeur de retour  
 L'argument `pp` casté en un pointeur\-vers\-un\-pointeur vers `void`.  
  
## Remarques  
 Une erreur de compilation est générée si le paramètre de modèle `T` ne dérive pas d'`IUnknown`.  
  
## Configuration requise  
 **En\-tête:** client.h  
  
## Voir aussi  
 [Reference \(Windows Runtime Library\)](http://msdn.microsoft.com/fr-fr/00000000-0000-0000-0000-000000000000)