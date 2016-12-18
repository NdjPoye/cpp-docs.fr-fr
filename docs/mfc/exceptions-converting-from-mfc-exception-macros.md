---
title: "Exceptions&#160;: conversion &#224; partir de macros d&#39;exception MFC | Microsoft Docs"
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
  - "catch (blocs), délimiter"
  - "CException (classe), supprimer des objets de classe CException"
  - "conversions, code écrit avec des macros MFC"
  - "convertir des exceptions"
  - "gestion des exceptions, convertir des exceptions"
  - "objets d'exception"
  - "objets d'exception, supprimer"
  - "exceptions, convertir"
  - "exceptions, supprimer des objets d'exception"
  - "mots clés (C++), macros"
  - "macros, mots clés C++"
ms.assetid: bd3ac3b3-f3ce-4fdd-a168-a2cff13ed796
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Exceptions&#160;: conversion &#224; partir de macros d&#39;exception MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ceci est une rubrique avancée.  
  
 Cet article explique comment convertir le code existant entre des macros de Microsoft Foundation Class \( **TRY**, **CATCH**, **THROW**, etc. — pour utiliser les mots clés de gestion des exceptions C\+\+ **try**, **catch**, et `throw`.  Les rubriques traitées ici sont les suivantes :  
  
-   [Avantages de conversion](#_core_advantages_of_converting)  
  
-   [Conversion de code avec des macros d'exception pour utiliser des exceptions C\+\+](#_core_doing_the_conversion)  
  
##  <a name="_core_advantages_of_converting"></a> Avantages de conversion  
 Vous n'avez probablement pas besoin de convertir le code existant, bien que vous devriez tenir compte des différences entre les implémentations de macro dans la version 3,0 de MFC et les implémentations dans les versions antérieures.  Ces différences et les modifications qui s'en suivent du comportement du code sont décrites dans [Exceptions : Modifications des macros d'exception de la version 3,0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md).  
  
 Les avantages de conversion sont :  
  
-   Le code qui utilise les compilations de mots clés de gestion des exceptions C\+\+ se compile en un .EXE ou un .DLL légèrement plus petit.  
  
-   Les mots clés de gestion des exceptions C\+\+ sont plus souples : Ils peuvent gérer les exceptions de tout type de données qui peuvent être copiées \(`int`, **float**, `char`, etc.\), tandis que les macros gèrent uniquement les exceptions de la classe `CException` et des classes dérivées de celle\-ci.  
  
 La différence majeure entre les macros et les mots clés est qu'utiliser les macros dans le code supprime "automatiquement" une exception interceptée lorsque l'exception passe hors de portée.  Ce n'est pas le cas en utilisant les mots clés en codant, vous devez explicitement supprimer une exception interceptée.  Pour plus d'informations, consultez l'article [Exceptions : Intercepter et Supprimer des exceptions](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
 L'autre différence est la syntaxe.  La syntaxe des macros et celle des mots clés différent à trois égards :  
  
1.  Les arguments de macro et déclarations d'exception :  
  
     Une invocation de macro **CATCH** présente la syntaxe suivante :  
  
     **CATCH\(** *classe\_d\_exception*, *nom\_pointeur\_objet\_exception* **\)**  
  
     Notez la virgule entre le nom de classe et le nom du pointeur de l'objet.  
  
     La déclaration d'exception du mot clé **catch** utilise cette syntaxe :  
  
     **catch\(** *type\_exception* *nom\_exception***\)**  
  
     Cette instruction de déclaration d'exception indique le type d'exception que le bloc CATCH gère.  
  
2.  Délimitation des blocs CATCH :  
  
     Avec les macros, la macro de **CATCH** \(avec ses arguments\) démarre le premier bloc CATCH ; la macro `AND_CATCH` démarre les blocs CATCH suivants, et la macro `END_CATCH` termine la séquence de blocs CATCH.  
  
     Avec les mots clés, le mot clé **catch** \(avec sa déclaration d'exception\) démarre chaque bloc CATCH.  Il n'y a pas de contrepartie à `END_CATCH`; le bloc CATCH se termine avec l'accolade fermante.  
  
3.  L'expression throw :  
  
     Les macros utilisent `THROW_LAST` pour relancer l'exception actuelle.  Le mot clé `throw`, sans l'argument, a le même effet.  
  
##  <a name="_core_doing_the_conversion"></a> Effectuer la conversion  
  
#### Pour convertir du code utilisant des macros et utiliser les mots clés de gestion des exceptions C\+\+  
  
1.  Recherchez toutes les occurrences des macros MFC **TRY**, **CATCH**, `AND_CATCH`, `END_CATCH`, **THROW**, et `THROW_LAST`.  
  
2.  Remplacez ou supprimez toutes les occurrences des macros suivantes :  
  
     **TRY** \(remplacez le par **try**\)  
  
     **CATCH** \(Remplacez\-le par **catch**\)  
  
     `AND_CATCH` \(Remplacez le par **catch**\)  
  
     `END_CATCH` \(supprimez le\)  
  
     **THROW** \(Remplacez le par `throw`\)  
  
     `THROW_LAST` \(Remplacez le par `throw`\)  
  
3.  Modifiez les arguments des macro afin qu'ils constituent des déclarations valides d'exception.  
  
     Par exemple, changez  
  
     [!code-cpp[NVC_MFCExceptions#6](../mfc/codesnippet/CPP/exceptions-converting-from-mfc-exception-macros_1.cpp)]  
  
     en  
  
     [!code-cpp[NVC_MFCExceptions#7](../mfc/codesnippet/CPP/exceptions-converting-from-mfc-exception-macros_2.cpp)]  
  
4.  Modifiez le code dans les blocs CATCH afin qu'il supprime les objets d'exception au besoin.  Pour plus d'informations, consultez l'article [Exceptions : Intercepter et Supprimer des exceptions](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
 Voici un exemple de code de gestion des exceptions utilisant les macros d'exception de MFC.  Notez que puisque le code dans l'exemple suivant utilise des macros, l'exception `e` est supprimée automatiquement :  
  
 [!code-cpp[NVC_MFCExceptions#8](../mfc/codesnippet/CPP/exceptions-converting-from-mfc-exception-macros_3.cpp)]  
  
 Le code dans l'exemple suivant utilise des mots clés d'exception C\+\+, l'exception doit être supprimée explicitement :  
  
 [!code-cpp[NVC_MFCExceptions#9](../mfc/codesnippet/CPP/exceptions-converting-from-mfc-exception-macros_4.cpp)]  
  
 Pour plus d'informations, consultez [Exceptions : À l'aide de la macro MFC et les exceptions C\+\+](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).  
  
## Voir aussi  
 [Gestion des exceptions](../mfc/exception-handling-in-mfc.md)