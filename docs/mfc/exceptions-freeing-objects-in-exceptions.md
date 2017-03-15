---
title: "Exceptions&#160;: lib&#233;ration d&#39;objets dans les exceptions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "détruire des objets"
  - "gestion des exceptions, détruire des objets"
  - "libérer des objets"
  - "gestion des exceptions locales"
  - "fuites de mémoire, provoquée par (exception)"
  - "lever des exceptions, après destruction"
  - "lever des exceptions, libérer des objets dans les exceptions"
  - "try-catch (gestion des exceptions), détruire des objets"
ms.assetid: 3b14b4ee-e789-4ed2-b8e3-984950441d97
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Exceptions&#160;: lib&#233;ration d&#39;objets dans les exceptions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique les besoins et la méthode pour libérer les objets lorsqu'une exception se produit.  Les rubriques traitées ici sont les suivantes :  
  
-   [Gestion de l'exception localement](#_core_handling_the_exception_locally)  
  
-   [Levaer des exceptions après une destruction d'objets](#_core_throwing_exceptions_after_destroying_objects)  
  
 Les exceptions levées par l'infrastructure ou par votre application interrompent le bon déroulement du programme.  Par conséquent, il est très important de suivre les objets afin que vous puissiez correctement les supprimer au cas où une exception est levée.  
  
 Il existe deux méthodes principales d'effectuer cette opération :  
  
-   Manipulez les exceptions localement à l'aide des mots clés **try** et **catch**, puis détruisez tous les objets avec une instruction.  
  
-   Détruisez un objet dans le bloc **catch** avant de lever l'exception en dehors du bloc pour une gestion future.  
  
 Ces deux méthodes sont illustrées ci\-dessous en tant que solutions à l'exemple problématique suivant :  
  
 [!code-cpp[NVC_MFCExceptions#14](../mfc/codesnippet/CPP/exceptions-freeing-objects-in-exceptions_1.cpp)]  
  
 Comme écrit ci\-dessus, `myPerson` n'est pas supprimé si une exception est levée par `SomeFunc`.  L'exécution accède directement au gestionnaire d'exceptions externe suivant, en ignorant la sortie standard de la fonction et le code qui supprime l'objet.  Le pointeur à l'objet sort de l'étendue lorsque l'exception part de la fonction, et la mémoire occupée par l'objet ne sera jamais récupérée tant que le programme s'exécute.  Il s'agit d'une fuite de mémoire ; elle est détectée à l'aide du diagnostic de mémoire.  
  
##  <a name="_core_handling_the_exception_locally"></a> Gestion locale de l'exception  
 Le paradigme **try\/catch** fournit une méthode de programmation défensive pour éviter des fuites de mémoire et vous assurer que les objets sont détruits quand des exceptions se produisent.  Par exemple, l'exemple indiqué précédemment dans cet article peut être réécrit comme suit :  
  
 [!code-cpp[NVC_MFCExceptions#15](../mfc/codesnippet/CPP/exceptions-freeing-objects-in-exceptions_2.cpp)]  
  
 Ce nouvel exemple configure un gestionnaire d'exceptions pour intercepter l'exception et la gérer localement.  Il quitte ensuite la fonction normalement et détruit l'objet.  Le point important de cet exemple est qu'un contexte pour intercepter l'exception est établi avec les blocs **try\/catch**.  Sans cadre local d'exception, la fonction ne saurait jamais qu'une exception a été levée et n'aurait pas l'occasion de se terminer normalement et de détruire l'objet.  
  
##  <a name="_core_throwing_exceptions_after_destroying_objects"></a> Lever des exceptions après une destruction d'objets  
 Une autre méthode pour la gestion des exceptions est de les transmettre au contexte externe suivant de gestion des exceptions.  Dans un bloc **catch**, vous pouvez effectuer le nettoyage de vos objets alloués localement puis lever une exception pour un traitement ultérieur.  
  
 La fonction levée peut ou ne peut pas avoir besoin de libérer les objets pile.  Si la fonction libère toujours l'objet pile avant le retour au cas ordinaire, la fonction doit également libérer l'objet pile avant de lever d'exception.  En revanche, si la fonction ne libère pas l'objet avant le retour au cas ordinaire, vous devez décider au cas par cas si l'objet pile doit être libéré.  
  
 L'exemple suivant montre comment les objets alloués localement peuvent être nettoyés :  
  
 [!code-cpp[NVC_MFCExceptions#16](../mfc/codesnippet/CPP/exceptions-freeing-objects-in-exceptions_3.cpp)]  
  
 Le mécanisme d'exception libère automatiquement les objets cadres ; le destructeur de l'objet cadre est également appelé.  
  
 Si vous appelez les fonctions qui peuvent lever des exceptions, vous pouvez utiliser des blocs **try\/catch** pour vérifier que vous interceptez des exceptions et que vous disposez d'une occasion de détruire tous les objets créés.  En particulier, sachez que de nombreuses fonctions de MFC peuvent lever des exceptions.  
  
 Pour plus d'informations, consultez [Exceptions : Interception et suppression des exceptions](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
## Voir aussi  
 [Gestion des exceptions](../mfc/exception-handling-in-mfc.md)