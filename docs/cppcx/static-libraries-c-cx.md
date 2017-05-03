---
title: "Biblioth&#232;ques statiques (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 10
---
# Biblioth&#232;ques statiques (C++/CX)
Une bibliothèque statique utilisée dans une application du [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] peut contenir du code conforme à la norme ISO C\+\+, notamment des types STL. Par ailleurs, elle appelle les API Win32 qui ne sont pas exclues de la plateforme d'application du [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]. Une bibliothèque statique consomme des composants [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] et peut créer des composants [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] avec certaines restrictions.  
  
## Création de bibliothèques statiques  
  
#### Pour créer une bibliothèque statique à utiliser dans une application [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)], effectuez les opérations ci\-dessous.  
  
1.  Dans la barre de menus, choisissez **Fichier** \> **Nouveau** \> **Projet** \> **Bibliothèque statique vide** pour les applications du [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)].  
  
2.  Dans l'**Explorateur de solutions**, ouvrez le menu contextuel du projet et choisissez **Propriétés**. Dans la boîte de dialogue **Propriétés**, dans la page **Propriétés de configuration** \> **Général**, définissez la prise en charge des applications du [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] à **Oui**.  
  
3.  Dans la page **Propriétés de configuration** \> **C\/C\+\+**, affectez la valeur **Oui \(\/ZW\)** à **Consommer** [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] **l’extension**.  
  
 Lorsque vous compilez une nouvelle bibliothèque statique, si vous appelez une API Win32 qui est exclue pour les applications [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)], le compilateur déclenche l’erreur C3861 « Identificateur introuvable ». Pour rechercher une autre méthode prise en charge pour le [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], consultez [Alternatives to Windows APIs in Windows Store apps](http://msdn.microsoft.com/fr-fr/75568012-61e0-41cc-a4df-c698f54f21ec).  
  
 Si vous ajoutez un projet de bibliothèque statique C\+\+ à une solution d'application [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)], vous devrez peut\-être mettre à jour les paramètres de propriété du projet de bibliothèque pour que la prise en charge des propriétés [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] soit définie sur **Oui**. Sans ce paramètre, le code est généré et crée des liens, mais une erreur se produit lorsque vous essayez de vérifier l'application pour [!INCLUDE[win8_appstore_long](../cppcx/includes/win8-appstore-long-md.md)]. La bibliothèque statique doit être compilée avec les mêmes paramètres de compilateur que ceux du projet qui la consomme.  
  
 Si vous consommez une bibliothèque statique qui crée des classes `ref` publiques, des classes d'interface publiques ou des classes de valeur publiques, l'éditeur de liens déclenche l'avertissement suivant :  
  
> **warning LNK4264:** archivage du fichier objet compilé avec \/ZW dans une bibliothèque statique ; notez que lors de la création de types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], il est déconseillé d’établir une liaison avec une bibliothèque statique qui contient des métadonnées [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)].  
  
 Vous pouvez ignorer en toute sécurité cet avertissement, à condition que la bibliothèque statique ne produise pas les composants [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] qui sont consommés en dehors de la bibliothèque elle\-même. Si la bibliothèque ne consomme pas un composant qu'elle définit, l'éditeur de liens peut optimiser l'implémentation même si les métadonnées publiques contiennent les informations de type. En d'autres termes, les composants publics d'une bibliothèque statique sont compilés mais ne sont pas activés au moment de l'exécution. C'est la raison pour laquelle tout composant [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] destiné à être consommé par d'autres composants ou d'autres applications doit être implémenté dans une bibliothèque de liens dynamiques \(DLL\).  
  
## Voir aussi  
 [Thread et Marshaling](../cppcx/threading-and-marshaling-c-cx.md)