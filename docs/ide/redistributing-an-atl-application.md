---
title: "Redistribution d&#39;une application ATL | Microsoft Docs"
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
  - "ATL, redistribuer"
  - "modèles OLE DB, redistribuer"
  - "redistribuer ATL"
  - "redistribuer les modèles OLE DB"
ms.assetid: 9a696b22-2345-43ec-826b-be7cb8cfd676
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Redistribution d&#39;une application ATL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

À compter de Visual Studio 2012, la bibliothèque ATL \(Active Template Library\) est une bibliothèque à en\-tête uniquement.  Les projets ATL ne possèdent pas d'option Lien dynamique vers ATL.  Aucun composant redistribuable de bibliothèque ATL n'est requis.  
  
 Si vous redistribuez une application ATL exécutable, vous devez inscrire le fichier .exe \(et tous les contrôles qu'il contient\) en émettant la commande suivante :  
  
```  
filename /regserver  
  
```  
  
 où `filename` est le nom du fichier exécutable.  
  
 Dans Visual Studio 2010, un projet ATL peut être généré pour une configuration MinDependency ou MinSize.  Une configuration MinDependency est le résultat que vous obtenez quand vous affectez à la propriété **Utilisation des ATL** la valeur **Lien statique vers ATL** dans la page de propriétés **Général** et quand vous affectez à la propriété **Bibliothèque Runtime** la valeur **Multithread \(\/MT\)** dans la page de propriétés **Génération de code** \(dossier C\/C\+\+\).  
  
 Une configuration MinSize est le résultat que vous obtenez quand vous affectez à la propriété **Utilisation des ATL** la valeur **Lien dynamique vers ATL** dans la page de propriétés **Général** ou quand vous affectez à la propriété **Bibliothèque Runtime** la valeur **DLL multithread \(\/MD\)** dans la page de propriétés **Génération de code** \(dossier C\/C\+\+\).  
  
 MinSize réduit autant que possible le fichier de sortie, mais nécessite que les fichiers ATL100.dll et Msvcr100.dll \(si vous avez sélectionné l'option **DLL multithread \(\/MD\)**\) se trouvent sur l'ordinateur cible.  Le fichier ATL100.dll doit être inscrit sur l'ordinateur cible pour garantir la présence de toutes les fonctionnalités ATL seront présentes.  ATL100.dll contient des exports ANSI et Unicode.  
  
 Si vous générez votre projet de modèles ATL ou OLE DB pour une cible MinDependency, il est inutile d'installer et d'inscrire ATL100.dll sur l'ordinateur cible, bien que vous puissiez obtenir une image de programme plus grande.  
  
 Pour les applications de modèles OLE DB, assurez\-vous que l'ordinateur cible dispose des dernières versions des fichiers Microsoft Data Access Components \(MDAC\).  Pour plus d'informations, consultez [Redistribution de fichiers de prise en charge de base de données](../ide/redistributing-database-support-files.md).  
  
## Voir aussi  
 [Redistribution des fichiers Visual C\+\+](../ide/redistributing-visual-cpp-files.md)