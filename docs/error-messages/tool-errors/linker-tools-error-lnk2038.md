---
title: "Erreur des outils &#201;diteur de liens LNK2038 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2038"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2038"
ms.assetid: b8d0fb35-eee6-4f52-b3c4-239cb4f65656
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Erreur des outils &#201;diteur de liens LNK2038
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

décalage détecté pour '\<nom\>': la valeur '\<valeur 1\>' ne correspond pas à la valeur '\<valeur 2\>' dans \<filename.obj\>  
  
 Un décalage de symbole a été détectée par l'éditeur de liens.  Cette erreur indique que différentes parties d'une application—cela inclut les bibliothèques ou autre objets auxquels l'application est liée—utilise des définitions contradictoires pour le symbole.  Le pragma [détecter l'incompatibilité](../../preprocessor/detect-mismatch.md) est utilisé pour définir de tels symboles et détecter leurs valeurs incompatibles.  
  
### Pour corriger cette erreur  
  
-   Cette erreur peut se produire lorsqu'un fichier objet dans votre projet est obsolète.  Avant d'essayer d'autres solutions à cette erreur, lancez une version nettoyée pour vérifier que les fichiers objets sont en cours.  
  
-   Visual Studio définit les symboles ci\-dessous pour empêcher la liaison de code incompatible, qui peut provoquer des erreurs d'exécution ou d'autres comportements inattendus.  
  
     `_MSC_VER`  
     Indique les numéros de version première et secondaire du compilateur Visual C\+\+ qui est utilisé pour générer une application ou une bibliothèque.  Du code qui est compilé à l'aide d'une version du compilateur Visual C\+\+ est incompatible avec du code compilé à l'aide d'une version qui a d'autres numéros de version première et secondaire.  Pour plus d'informations, consultez `_MSC_VER` dans [Macros prédéfinies](../../preprocessor/predefined-macros.md).  
  
     Si vous faites le lien avec une bibliothèque qui n'est pas compatible avec la version du compilateur Visual C\+\+ que vous utilisez, et si vous ne pouvez pas obtenir ou générer une version compatible de la bibliothèque, vous pouvez utiliser une version antérieure du compilateur pour générer votre projet— changez uniquement la propriété **Ensemble d'outils de la plateforme** du projet.  Pour plus d'informations, consultez [comment : modifier la version cible de .Net Framework et l'ensemble d'outils de la plateforme](../../build/how-to-modify-the-target-framework-and-platform-toolset.md).  
  
     `_ITERATOR_DEBUG_LEVEL`  
     Indique le niveau de sécurité et les fonctionnalités de débogage qui sont activées dans la bibliothèque standard C\+\+.  Ces fonctionnalités peuvent modifier la représentation de certains objets standard de la bibliothèque C\+\+ et ainsi les rendre incompatibles avec celles qui utilisent d'autres fonctionnalités de sécurité et de débogage.  Pour plus d'informations, consultez [\_ITERATOR\_DEBUG\_LEVEL](../../standard-library/iterator-debug-level.md).  
  
     `RuntimeLibrary`  
     Indique la version de la bibliothèque standard C\+\+ et du runtime C qui est utilisé par une application ou une bibliothèque.  Le code qui utilise une version de bibliothèque standard C\+\+ ou du runtime C est incompatible avec du code qui utilise une version différente.  Pour plus d'informations, consultez [\/MD, \/MT, \/LD \(Utiliser la bibliothèque Runtime\)](../../build/reference/md-mt-ld-use-run-time-library.md).  
  
     `_PPLTASKS_WITH_WINRT`  
     Indique que du code qui utilise la [Bibliothèque de modèles parallèles \(PPL\)](../../parallel/concrt/parallel-patterns-library-ppl.md) est lié aux objets compilés en utilisant un paramètre différent pour l'option [\/ZW](../../build/reference/zw-windows-runtime-compilation.md) du compilateur. \(**\/ZW** prend en charge c\+\+\/CX.\) Du code qui utilise ou dépend des PPL doit être compilé en utilisant le même paramètre **\/ZW** que celui utilisé dans le reste de l'application.  
  
     Assurez\-vous que les valeurs de ces symboles soient cohérentes dans tous les projets de votre solution Visual Studio, et également qu'elles sont compatibles avec le code et les bibliothèques auxquels votre application est lié.  
  
## Voir aussi  
 [Erreurs et avertissements des outils Éditeur de liens](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)