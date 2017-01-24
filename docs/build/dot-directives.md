---
title: "Directives pr&#233;c&#233;d&#233;es par un point | Microsoft Docs"
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
  - "directives précédées par un point dans NMAKE"
  - "programme NMAKE, directives précédées par un point"
ms.assetid: ab35da65-30b6-48b7-87d6-61503d7faf9f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Directives pr&#233;c&#233;d&#233;es par un point
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifiez des directives précédées par un point en dehors d'un bloc de description, au début d'une ligne.  Les directives précédées par un point commencent par un point \(. \) et sont suivies par un signe deux\-points \(:\).  Les espaces et les tabulations ne sont pas admis.  Les noms des directives précédées par un point respectent la casse et sont en majuscules.  
  
|Directive|Objectif|  
|---------------|--------------|  
|**.IGNORE :**|Ignore les codes de sortie autres que zéro retournés par les commandes, de l'emplacement où elle est spécifiée jusqu'à la fin du makefile.  Par défaut, NMAKE s'arrête si une commande retourne un code de sortie différent de zéro.  Pour rétablir la vérification des erreurs, utilisez **\!CMDSWITCHES**.  Pour ne pas tenir compte du code de sortie d'une seule commande, utilisez le modificateur tiret \(–\).  Pour ignorer les codes de sortie d'un fichier entier, utilisez l'option \/I.|  
|**.PRECIOUS :** *cibles*|Conserve les *cibles* sur le disque si les commandes destinées à les mettre à jour sont arrêtées ; reste sans effet si une commande gère une interruption en supprimant le fichier.  Séparez les noms des cibles par un ou plusieurs espaces ou tabulations.  Par défaut, NMAKE supprime une cible en cas d'interruption d'une génération par une combinaison CTRL\+C ou CTRL\+ATTN.  L'utilisation de **.PRECIOUS** s'applique à tout le makefile ; les spécifications multiples sont cumulatives.|  
|**.SILENT :**|Supprime l'affichage des commandes exécutées, de l'emplacement où elle est spécifiée jusqu'à la fin du makefile.  Par défaut, NMAKE affiche les commandes qu'il appelle.  Pour rétablir l'écho, utilisez **\!CMDSWITCHES**.  Pour supprimer l'écho d'une seule commande, utilisez le modificateur **@**.  Pour supprimer l'écho pour un fichier entier, utilisez l'option \/S.|  
|**.SUFFIXES :** `list`|Répertorie les extensions pour la mise en correspondance des règles d'inférence ; les extensions sont prédéfinies pour inclure les extensions suivantes : exe .obj .asm .c .cpp .cxx .bas .cbl .for .pas .res .rc .f .f90|  
  
 Pour modifier l'ordre de la liste **.SUFFIXES** ou définir une nouvelle liste, supprimez la liste et définissez une nouvelle configuration.  Pour supprimer la liste, spécifiez une absence d'extensions après le signe deux points :  
  
```  
.SUFFIXES :  
```  
  
 Pour ajouter d'autres suffixes à la fin de la liste, indiquez  
  
```  
.SUFFIXES : suffixlist  
```  
  
 où *suffixlist* est une liste de suffixes supplémentaires, séparés par un ou plusieurs espaces ou tabulations.  Pour visualiser la configuration en cours de **.SUFFIXES**, exécutez NMAKE avec l'option \/P.  
  
## Voir aussi  
 [Référence NMAKE](../build/nmake-reference.md)