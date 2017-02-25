---
title: "HStringReference::HStringReference, constructeur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference"
dev_langs: 
  - "C++"
ms.assetid: 29f5fe11-3928-4f60-9861-f0894247bfcb
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# HStringReference::HStringReference, constructeur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialise une nouvelle instance de la classe HStringReference.  
  
## Syntaxe  
  
```cpp  
  
    template<unsigned int sizeDest>  
    HStringReference(wchar_t const (&str)[ sizeDest]) throw();  
  
    template<unsigned int sizeDest>  
    HStringReference(wchar_t const (&str)[ sizeDest],   
unsigned int len)  
       throw();  
  
    HStringReference(HStringReference&& other) throw();  
  
```  
  
#### Paramètres  
 `sizeDest`  
 Un paramètre de modèle spécifiant la taille de la mémoire tampon du HStringReference de destination.  
  
 `str`  
 Une référence à une chaîne à caractères larges.  
  
 `len`  
 La longueur maximale de la mémoire tampon du paramètre `str` à utiliser dans cette opération.  Si le paramètre `len` n'est pas spécifié, le paramètre `str` entier est utilisé.  Si `len` est supérieur à `sizeDest`, `len` a la valeur `sizeDest`\-1.  
  
 `other`  
 Un autre objet de HStringReference.  
  
## Remarques  
 Le premier constructeur initialise un objet de HStringReference de la même taille qu'un paramètre `str`.  
  
 Le deuxième constructeur initialise un objet de HStringReference dont la taille est spécifiée par le paramètre `len`.  
  
 Le troisième constructeur initialise un objet de HStringReference à la valeur du paramètre `other`, puis détruit le paramètre `other` .  
  
## Configuration requise  
 **En\-tête:** corewrappers.h  
  
 **Espace de noms:** Microsoft::WRL::Wrappers  
  
## Voir aussi  
 [HStringReference, classe](../windows/hstringreference-class.md)