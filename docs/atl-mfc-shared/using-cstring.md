---
title: "Using CString | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CString class (Visual C++)"
  - "CString objects, C++ string manipulation"
  - "CString objects, reference counting"
ms.assetid: ed018aaf-8b10-46f9-828c-f9c092dc7609
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Using CString
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les rubriques de cette section décrivent comment programmer avec `CString`.  Pour une documentation de référence sur la classe `CString`, consultez la documentation de [CStringT](../atl-mfc-shared/reference/cstringt-class.md).  
  
 Pour utiliser `CString`, incluez l'en\-tête `atlstr.h`.  
  
 Les classes `CString`, `CStringA` et `CStringW` sont des spécialisations d'un modèle de classe nommé [CStringT](../atl-mfc-shared/reference/cstringt-class.md), basées sur type de données caractères qu'elles prennent en charge.  
  
 Un objet `CStringW` contient le type `wchar_t` et prend en charge les chaînes Unicode.  Un objet `CStringA` contient le type `char` et prend en charge les chaînes sur un octet et les chaînes multi\-octets \(MBCS\).  Un objet `CString` prend en charge le type `char` ou le type `wchar_t`, selon que le symbole `MBCS` ou le symbole `UNICODE` est défini à la compilation.  
  
 Un objet `CString` conserve les données caractères dans un objet `CStringData`.  `CString` accepte les chaînes de style C terminées par `null`, mais ne conserve pas le caractère `null` dans les données caractères stockées.  Au lieu de cela, `CString` fait le suivi de la longueur de la chaîne.  `CString` fournit un terminateur null quand il exporte une chaîne de style C.  Vous pouvez insérer un caractère `null` dans une chaîne `CString`, mais cela peut produire des résultats inattendus.  
  
 L'ensemble suivant de classes de chaîne peut être utilisé sans liaison avec la bibliothèque MFC, avec ou sans prise en charge de CRT : `CAtlString`, `CAtlStringA` et `CAtlStringW`.  
  
 `CString` est utilisé dans les projets natifs.  Pour les projets en code managé \(C\+\+\/CLI\), utilisez `System::String`.  
  
 Pour ajouter davantage de capacités à celles actuellement offertes par `CString`, `CStringA` ou `CStringW`, vous devez créer une sous\-classe de `CStringT` qui contient les fonctionnalités supplémentaires.  
  
 Le code suivant montre comment créer un objet `CString` et l'imprimer dans la sortie standard :  
  
```cpp  
#include <atlstr.h>  
  
int main() {  
    CString aCString = CString(_T("A string"));  
    _tprintf(_T("%s"), (LPCTSTR) aCString);  
}  
```  
  
## Dans cette section  
 [Opérations CString de base](../atl-mfc-shared/basic-cstring-operations.md)  
 Décrit les opérations `CString` de base, y compris la création d'objets à partir de chaînes littérales C, l'accès à des caractères individuels d'un objet `CString`, la concaténation de deux objets et la comparaison d'objets `CString`.  
  
 [Gestion des données chaînes](../atl-mfc-shared/string-data-management.md)  
 Présente l'utilisation de Unicode et MBCS avec `CString`.  
  
 [Sémantique CString](../atl-mfc-shared/cstring-semantics.md)  
 Explique comment les objets `CString` sont utilisés.  
  
 [Opérations CString relatives aux chaînes de style C](../atl-mfc-shared/cstring-operations-relating-to-c-style-strings.md)  
 Décrit la manipulation du contenu d'un objet `CString` sous la forme d'une chaîne de style C terminée par un caractère null.  
  
 [Allocation et libération de mémoire pour un BSTR](../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)  
 Présente l'utilisation de la mémoire pour un `BSTR` et des objets COM.  
  
 [Nettoyage des exceptions CString](../atl-mfc-shared/cstring-exception-cleanup.md)  
 Explique qu'un nettoyage explicite dans MFC 3.0 et ultérieur n'est plus nécessaire.  
  
 [Passage d'arguments CString](../atl-mfc-shared/cstring-argument-passing.md)  
 Explique comment passer des objets CString à des fonctions et comment retourner des objets `CString` depuis des fonctions.  
  
 [Prise en charge des jeux de caractères Unicode et MCBS \(Multibyte Character Set\)](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)  
 Explique comment MFC prend en charge Unicode et MBCS.  
  
## Référence  
 [CStringT](../atl-mfc-shared/reference/cstringt-class.md)  
 Fournit des informations de référence sur la classe `CStringT`.  
  
 [CSimpleStringT Class](../atl-mfc-shared/reference/csimplestringt-class.md)  
 Fournit des informations de référence sur la classe `CSimpleStringT`.  
  
## Rubriques connexes  
 [Chaînes](../atl-mfc-shared/strings-atl-mfc.md)  
 Contient des liens vers des rubriques décrivant plusieurs façons de gérer les données chaînes.  
  
 [Instanciation du modèle de classe](../Topic/Class%20Template%20Instantiation.md)  
 `CString` est un `typedef` basé sur `CStringT`, qui est une instance d'une spécialisation d'un modèle de classe.