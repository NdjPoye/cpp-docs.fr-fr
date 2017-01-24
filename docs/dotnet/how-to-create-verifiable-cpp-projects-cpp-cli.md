---
title: "Comment&#160;: cr&#233;er des projets C++ v&#233;rifiables (C++/CLI) | Microsoft Docs"
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
  - "conversions, projets C++"
  - "assemblys vérifiables (C++), créer"
  - "projets Visual C++"
ms.assetid: 4ef2cc1a-e3e5-4d67-8d8d-9c614f8ec5d3
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: cr&#233;er des projets C++ v&#233;rifiables (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les Assistants Application Visual C\+\+ ne créent pas de projets vérifiables, mais les projets peuvent être convertis pour être vérifiables.  Cette rubrique explique comment modifier les propriétés de projet et modifier les fichiers sources de projet pour transformer vos projets Visual C\+\+ en vue de produire des applications vérifiables.  
  
## Paramètres du Compilateur et de l'Éditeur de liens  
 Par défaut, les projets .NET utilisent l'indicateur du compilateur \/clr et configurent l'éditeur de liens pour viser le matériel de x86.  Pour le code vérifiable, vous devez utiliser l'indicateur \/clr:safe, et vous devez indiquer à l'éditeur de liens de générer le MSIL à la place d'instructions machine natives.  
  
#### Pour modifier les paramètres du compilateur et de l'éditeur de liens  
  
1.  Affichez la page de propriétés du projet.   Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../misc/how-to-open-project-property-pages.md).  
  
2.  Dans la page **Général** sous le nœud **Propriétés de configuration**, affectez à la propriété **Prise en charge du Common Language Runtime** la valeur **Prise en charge du Common Language Runtime MSIL sécurisé \(\/clr:safe\)**.  
  
3.  Dans la page **Avancé** sous le nœud **Éditeur de liens**, affectez à la propriété **Type d'image CLR** la valeur **Forcer l'image IL sécurisée \(\/CLRIMAGETYPE:SAFE\)**.  
  
## Suppression de types de données natifs  
 Dans la mesure où les types de données natifs sont non vérifiables, même s'ils ne sont pas utilisés réellement, vous devez supprimer tous les fichiers d'en\-tête qui contiennent des types natifs.  
  
> [!NOTE]
>  La procédure suivante s'applique à Application Windows Forms \(.NET\) et aux projets Application console \(.NET\).  
  
#### Pour supprimer des références aux types de données natifs  
  
1.  Supprimez tout le contenu du fichier Stdafx.h.  
  
## Configuration d'un point d'entrée  
 Vu que les applications vérifiables ne peuvent pas utiliser les bibliothèques Runtime C \(CRT\), elles ne peuvent pas compter sur le CRT pour appeler la fonction principale comme point d'entrée standard.  Cela signifie que vous devez fournir explicitement le nom de la fonction à appeler initialement à l'éditeur de liens. \(Dans ce cas, Main\(\) est utilisé au lieu de main\(\) ou \_tmain\(\) pour indiquer un point d'entrée non\-CRT, mais comme le point d'entrée doit être spécifié explicitement, ce nom est arbitraire.\)  
  
> [!NOTE]
>  Les procédures suivantes s'appliquent aux projets Application console \(.NET\).  
  
#### Pour configurer un point d'entrée  
  
1.  Remplacez \_tmain \(\) par Main \(\) dans le fichier .cpp principal du projet.  
  
2.  Affichez la page de propriétés du projet.   Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../misc/how-to-open-project-property-pages.md).  
  
3.  Dans la page **Avancé** sous le nœud **Éditeur de liens**, entrez `Main` comme valeur de propriété de **Point d'entrée**.  
  
## Voir aussi  
 [Code pur et vérifiable](../dotnet/pure-and-verifiable-code-cpp-cli.md)