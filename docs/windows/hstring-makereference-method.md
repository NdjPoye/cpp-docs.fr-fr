---
title: "HString::MakeReference, m&#233;thode | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference"
dev_langs: 
  - "C++"
ms.assetid: 9e1fd2b2-66ad-4a50-b647-a20ab10e522f
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString::MakeReference, m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Crée un objet HStringReference à partir d'une chaîne spécifiée en paramètre.  
  
## Syntaxe  
  
```  
template<unsigned int sizeDest>  
    static HStringReference MakeReference(  
              wchar_t const (&str)[ sizeDest]);  
  
    template<unsigned int sizeDest>  
    static HStringReference MakeReference(  
              wchar_t const (&str)[sizeDest],   
              unsigned int len);  
```  
  
#### Paramètres  
 `sizeDest`  
 Un paramètre de modèle spécifiant la taille de la mémoire tampon du HStringReference de destination.  
  
 `str`  
 Une référence à une chaîne à caractères larges.  
  
 `len`  
 La longueur maximale de la mémoire tampon du paramètre `str` à utiliser dans cette opération.  Si le paramètre `len` n'est pas spécifié, le paramètre `str` entier est utilisé.  
  
## Valeur de retour  
 Un objet HStringReference dont la valeur est la même que le paramètre `str` spécifié.  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [HString, classe](../windows/hstring-class.md)