---
title: "COM Interop Wrapper Error | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.cannotcopyassembly"
  - "Vs.refruntlbimp"
helpviewer_keywords: 
  - "COM Interop Wrapper dialog box"
ms.assetid: 9a9d6374-ee26-4dbc-9e34-e1d90f6254b4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# COM Interop Wrapper Error
Cette boîte de message s'affiche lorsque le système de projet ne peut pas créer un wrapper COM interop pour un composant particulier.  Les wrappers COM interop sont requis par le Common Language Runtime \(CLR\) pour gérer les composants COM et communiquer avec eux.  Pour plus d'informations, consultez [Interopérabilité COM en Visual Basic et Visual C\#](../Topic/COM%20Interoperability%20in%20.NET%20Framework%20Applications%20\(Visual%20Basic\).md).  
  
 Les causes courantes de l'échec incluent :  
  
-   La bibliothèque de types pour le composant n'est pas inscrite convenablement.  
  
-   Un composant dont dépend le composant encapsulé est introuvable sur votre ordinateur.  
  
 Dans ces deux cas, vous devez vérifier que le composant COM est installé et inscrit convenablement sur votre ordinateur et recommencer l'opération.  
  
> [!TIP]
>  Vous pouvez également rechercher sur le [site web MSDN](http://go.microsoft.com/fwlink/?LinkId=3355) un wrapper COM Interop qui aurait été publié pour votre composant COM.  
  
> [!NOTE]
>  Les wrappers COM Interop sont parfois appelés « assemblys PIA \(Primary Interop Assembly\) ». Ces termes sont synonymes.  
  
## Voir aussi  
 [Espace de noms de modèles de composants dans Visual Studio](http://msdn.microsoft.com/fr-fr/705d0add-0707-44ba-a6de-637381d9c937)   
 [Component Authoring](../Topic/Component%20Authoring.md)   
 [COM Interop](../Topic/COM%20Interop%20\(Visual%20Basic\).md)   
 [Common Language Runtime](../Topic/Common%20Language%20Runtime%20\(CLR\).md)   
 [COM Interoperability in .NET Framework Applications](../Topic/COM%20Interoperability%20in%20.NET%20Framework%20Applications%20\(Visual%20Basic\).md)