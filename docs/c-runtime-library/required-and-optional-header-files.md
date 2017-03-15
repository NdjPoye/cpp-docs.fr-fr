---
title: "Fichiers d&#39;en-t&#234;te requis et facultatifs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.headers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers d'en-tête, requis au moment de l'exécution"
  - "fichiers Include, requis au moment de l'exécution"
ms.assetid: f64d0bf5-e2c3-4b42-97d0-443b3d901d9f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Fichiers d&#39;en-t&#234;te requis et facultatifs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La description de chaque routine run\-time contient une liste des inclusions requises et optionelles, ou des en tetes \(.H\), fichiers pour cette routine.  Les fichiers d'en\-tête requis doivent être inclus pour obtenir la déclaration de fonction pour la routine ou une définition utilisée par une autre routine appelée en interne.  Les fichiers d'en\-tête facultatifs sont généralement inclus pour tirer parti des constantes prédéfinies, les définitions de type, ou des macros intégrées.  Le tableau suivant répertorie des exemples de contenu facultatif du fichier d'en\-tête :  
  
|Définition|Exemple|  
|----------------|-------------|  
|Définition de macro|Si une routine de bibliothèque est implémentée comme une macro, la définition de la macro peut être dans un fichier d'en\-tête différent du fichier d'en\-tête de la routine d'origine.  Par exemple, la macro `_toupper` est définie dans le fichier d'en\-tête CTYPE.H, tandis que la fonction `toupper` est déclarée dans. STDLIB.H.|  
|Constante prédéfinie|De nombreuses routines de bibliothèque font référence aux constantes définies dans les fichiers d'en\-tête.  Par exemple, la routine `_open` utilise des constantes comme `_O_CREAT`, qui est défini dans le fichier d'en\-tête FCNTL.H.|  
|Définition de types|Certaines routines de bibliothèque retournent une structure ou prenez une structure comme argument.  Par exemple, les routines de flux d'entrée\/sortie utilisent une structure de type `FILE`, qui est définie dans. STDIO.H.|  
  
 Les fichiers d'en\-tête de la bibliothèque d'exécutables fournissent des déclarations de la fonction dans le style recommandé par le standard ANSI\/ISO C.  Le compilateur effectue une vérification de type sur toute référence standard qui se produit après sa déclaration de fonction associée.  Les déclarations de fonction sont particulièrement importantes pour les routines qui retournent une valeur d'un type autre que `int`, qui est la valeur par défaut.  Les routines qui ne spécifient pas leurs valeurs de retour appropriées dans leur déclaration sont considérées comme par le compilateur pour renvoyer un `int`, ce qui peut générer des résultats inattendus.  Pour plus d'informations, consultez [Descripteur de type](../c-runtime-library/type-checking-crt.md).  
  
## Voir aussi  
 [Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md)