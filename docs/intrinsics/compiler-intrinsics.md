---
title: "compilateur, intrins&#232;ques | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compilateur cl.exe, intrinsèques"
  - "compilateur cl.exe, performances"
  - "compilateur (intrinsèques)"
  - "intrinsèques, compilateur"
ms.assetid: 48bb9929-7d78-4fd8-a092-ae3c9f971858
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# compilateur, intrins&#232;ques
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La plupart des fonctions sont contenues dans des bibliothèques, mais certaines sont intégrées au compilateur \(c'est\-à\-dire intrinsèques\).  On les appelle des fonctions intrinsèques ou tout simplement des intrinsèques.  
  
## Notes  
 Si une fonction est intrinsèque, le code de cette fonction est généralement inséré inline, ce qui évite la surcharge liée à un appel de fonction et permet d'exécuter des instructions machine hautement efficaces pour cette fonction.  Une intrinsèque est souvent plus rapide que l'assembly inline équivalent, car l'optimiseur a une connaissance intégrée du comportement de nombreuses intrinsèques. Certaines optimisations peuvent ainsi être disponibles, alors qu'elles ne le sont pas quand un assembly inline est utilisé.  De plus, l'optimiseur peut développer l'intrinsèque différemment, aligner les mémoires tampons différemment ou apporter d'autres ajustements en fonction du contexte et des arguments de l'appel.  
  
 L'utilisation d'intrinsèques affecte la portabilité du code, car les intrinsèques disponibles dans Visual C\+\+ peuvent ne pas être disponibles si le code est compilé avec d'autres compilateurs et certaines intrinsèques qui peuvent être disponibles pour certaines architectures cibles ne sont pas disponibles pour toutes les architectures.  Toutefois, les intrinsèques sont généralement plus portables que les assemblys inline.  Les intrinsèques sont nécessaires sur les architectures 64 bits où les assemblys inline ne sont pas pris en charge.  
  
 Certaines intrinsèques, telles que `__assume` et `__ReadWriteBarrier`, fournissent des informations au compilateur, ce qui affecte le comportement de l'optimiseur.  
  
 Certaines intrinsèques ne sont disponibles que sous la forme d'intrinsèques, tandis que d'autres sont disponibles à la fois dans des implémentations de fonctions et des implémentations intrinsèques.  Vous pouvez demander au compilateur d'utiliser l'implémentation intrinsèque de deux façons, selon que vous souhaitez activer uniquement des fonctions spécifiques ou activer toutes les intrinsèques.  La première approche consiste à utiliser `#pragma intrinsic(``intrinsic-function-name-list``)`.  Le pragma peut servir à spécifier une ou plusieurs intrinsèques séparées par des virgules.  La seconde approche consiste à utiliser l'option du compilateur [\/Oi \(Générer des fonctions intrinsèques\)](../build/reference/oi-generate-intrinsic-functions.md), qui rend disponibles toutes les intrinsèques sur une plateforme donnée.  Sous **\/Oi**, utilisez `#pragma function(``intrinsic-function-name-list``)` pour forcer l'utilisation d'un appel de fonction au lieu d'une intrinsèque.  Si la documentation d'une intrinsèque spécifique indique que la routine est disponible uniquement comme intrinsèque, l'implémentation intrinsèque est utilisée dans tous les cas \(que vous spécifiiez **\/Oi** ou `#pragma intrinsic` \).  Dans tous les cas, **\/Oi** ou `#pragma intrinsic` autorise, mais n'oblige pas, l'optimiseur à utiliser l'intrinsèque.  L'optimiseur peut toujours appeler la fonction.  
  
 Certaines fonctions de bibliothèque C\/C\+\+ standard sont disponibles dans des implémentations intrinsèques sur certaines architectures.  Lors de l'appel d'une fonction CRT, l'implémentation intrinsèque est utilisée si **\/Oi** est spécifié sur la ligne de commande.  
  
 Un fichier d'en\-tête, \<intrin.h\>, est disponible. Il déclare des prototypes pour les fonctions intrinsèques communes.  Les intrinsèques spécifiques au fabricant sont disponibles dans les fichiers d'en\-tête \<immintrin.h\> et \<ammintrin.h\>.  En outre, certains en\-têtes Windows déclarent des fonctions qui mappent à une intrinsèque du compilateur.  
  
 Les sections suivantes répertorient toutes les intrinsèques qui sont disponibles sur différentes architectures.  Pour plus d'informations sur le fonctionnement des intrinsèques sur votre processeur cible spécifique, consultez la documentation de référence du fabricant.  
  
-   [Fonctions ARM intrinsèques](../intrinsics/arm-intrinsics.md)  
  
-   [Liste d'intrinsèques x86](../intrinsics/x86-intrinsics-list.md)  
  
-   [Liste d'intrinsèques x64 \(amd64\)](../intrinsics/x64-amd64-intrinsics-list.md)  
  
-   [Intrinsèques disponibles sur toutes les architectures](../intrinsics/intrinsics-available-on-all-architectures.md)  
  
-   [Liste alphabétique des fonctions intrinsèques](../intrinsics/alphabetical-listing-of-intrinsic-functions.md)  
  
## Voir aussi  
 [ARM Assembler Reference](../assembler/arm/arm-assembler-reference.md)   
 [Microsoft Macro Assembler Reference](../assembler/masm/microsoft-macro-assembler-reference.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Référence sur les bibliothèques Runtime C](../c-runtime-library/c-run-time-library-reference.md)