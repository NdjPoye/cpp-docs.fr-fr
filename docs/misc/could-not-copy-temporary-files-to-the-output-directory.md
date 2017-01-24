---
title: "Impossible de copier les fichiers temporaires dans le r&#233;pertoire de sortie | Microsoft Docs"
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
  - "vs.tasklisterror.cannot_copy_to_run_dir"
ms.assetid: b8b54984-74c9-4b9b-8164-d0d13c141055
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Impossible de copier les fichiers temporaires dans le r&#233;pertoire de sortie
Le système de projet n’a pas pu copier les fichiers temporaires dans le répertoire de sortie. Les compilateurs génèrent toujours les fichiers dans des répertoires intermédiaires, par exemple, dans obj\\`configname`. À la fin du processus de build, le système de projet copie les fichiers du répertoire intermédiaire dans le répertoire de sortie du projet.  
  
 Ce problème peut se produire quand un des assemblys que vous compilez a une taille supérieure à 64 kilo\-octets \(Ko\) et qu’une des conditions suivantes \(ou les deux\) est vraie :  
  
-   Votre solution contient plusieurs projets qui sont compilés dans le même dossier de sortie.  
  
-   La propriété Copie locale est définie sur False pour l’un des assemblys ou projets référencés.  
  
 **Pour corriger cette erreur**  
  
-   Compilez les sorties de chacun des projets dans des dossiers différents.  
  
-   Définissez la propriété Copie locale de l’assembly ou du projet référencé sur True.  
  
-   Vérifiez que la fenêtre Explorateur d’objets n’est pas ouverte.  
  
-   Vérifiez qu’aucun projet identique n’est ouvert dans une autre instance de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
## Voir aussi  
 [NIB : Comment définir la propriété Copie locale d’une référence](http://msdn.microsoft.com/fr-fr/dfe2ba13-f27f-4356-a481-ea67d5acacbd)