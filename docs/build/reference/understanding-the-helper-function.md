---
title: "Pr&#233;sentation de la fonction d&#39;assistance | Microsoft Docs"
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
  - "__delayLoadHelper (fonction)"
  - "__delayLoadHelper2 (fonction)"
  - "chargement différé de DLL, fonction d'assistance"
  - "delayhlp.cpp"
  - "delayimp.h"
  - "delayimp.lib"
  - "fonctions d'assistance"
ms.assetid: 6279c12c-d908-4967-b0b3-cabfc3e91d3d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Pr&#233;sentation de la fonction d&#39;assistance
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La fonction d'assistance pour le chargement différé pris en charge par l'éditeur de liens est l'élément qui assure effectivement le chargement de la DLL au moment de l'exécution.  Vous pouvez la modifier pour personnaliser son comportement en écrivant votre propre fonction et en la liant à votre programme au lieu d'utiliser la fonction d'assistance fournie dans Delayimp.lib.  Une fonction d'assistance prend en charge toutes les DLL à chargement différé.  
  
 Vous pouvez fournir votre propre version de la fonction d'assistance si vous souhaitez un traitement spécifique en fonction des noms des DLL ou des importations.  
  
 La fonction d'assistance assure les opérations suivantes :  
  
-   Vérification du handle stocké vers la bibliothèque pour vérifier s'il a déjà été chargé.  
  
-   Appel de **LoadLibrary** pour tenter le chargement de la DLL  
  
-   Appel de **GetProcAddress** pour tenter d'obtenir l'adresse de la procédure.  
  
-   Retour au thunk de chargement différé des importations pour appeler le point d'entrée chargé  
  
 La fonction d'assistance peut rappeler un raccordement de notification dans votre programme après chacune des situations suivantes :  
  
-   Au démarrage de la fonction d'assistance  
  
-   Juste avant l'appel à **LoadLibrary** dans la fonction d'assistance  
  
-   Juste avant l'appel à **GetProcAddress** dans la fonction d'assistance  
  
-   En cas d'échec de l'appel à **LoadLibrary** dans la fonction d'assistance  
  
-   En cas d'échec de l'appel à **GetProcAddress** dans la fonction d'assistance  
  
-   Après la fin du traitement par la fonction d'assistance  
  
 Chacun de ces points de raccordement peut retourner une valeur qui modifie d'une certaine façon le traitement normal de la routine d'assistance, à l'exception du thunk de chargement différé des importations.  
  
 Le code de la fonction d'assistance par défaut se situe dans Delayhlp.cpp et Delayimp.h \(dans vc\\include\) et est compilé dans Delayimp.lib \(dans vc\\lib\).  Si vous ne créez pas votre propre fonction d'assistance, vous devez inclure cette bibliothèque dans vos compilations.  
  
 Les rubriques suivantes décrivent la fonction d'assistance :  
  
-   [Modifications apportées à la fonction d'assistance du chargement différé des DLL depuis Visual C\+\+ 6.0](../../build/reference/changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)  
  
-   [Conventions d'appel, paramètres et type de retour](../../build/reference/calling-conventions-parameters-and-return-type.md)  
  
-   [Définitions des structures et constantes](../../build/reference/structure-and-constant-definitions.md)  
  
-   [Calcul des valeurs nécessaires](../../build/reference/calculating-necessary-values.md)  
  
-   [Déchargement d'une DLL à chargement différé](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
## Voir aussi  
 [Prise en charge de l'éditeur de liens pour les DLL à chargement différé](../../build/reference/linker-support-for-delay-loaded-dlls.md)