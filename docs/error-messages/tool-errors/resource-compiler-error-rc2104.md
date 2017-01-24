---
title: "Erreur RC2104 du compilateur de ressources  | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC2104"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2104"
ms.assetid: 792a3bd8-cb4c-4817-b288-4ce37082b582
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur RC2104 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

mot clé ou nom de clé non défini : clé  
  
 Le mot clé ou le nom de clé spécifié n'est pas défini.  
  
 Cette erreur est souvent due à une erreur typographique dans la définition de la ressource ou dans le fichier d'en\-tête inclus.  Elle peut aussi être liée à un fichier d'en\-tête manquant.  
  
 Pour résoudre ce problème, recherchez le fichier d'en\-tête qui doit contenir le mot clé ou le nom de clé défini et vérifiez qu'il est inclus dans votre fichier de ressources. Assurez\-vous aussi que le mot clé ou le nom de clé est correctement orthographié.  Si votre projet a été créé avec un en\-tête précompilé et que vous le supprimez par la suite, assurez\-vous que le fichier de ressources contient toujours les en\-têtes nécessaires.  
  
 Pour vérifier les mots clés et noms de clé définis dans votre fichier de ressources, dans Visual Studio, ouvrez la fenêtre **Affichage des ressources** \(dans la barre de menus, choisissez **Affichage**, **Affichage des ressources**\), puis ouvrez le menu contextuel pour le fichier .rc et choisissez **Symboles des ressources** pour afficher la liste des symboles définis.  Pour modifier les en\-têtes inclus, ouvrez le menu contextuel pour le fichier .rc et choisissez **Include des ressources**.  
  
 Si vous obtenez le message suivant :  
  
```  
undefined keyword or key name: MFT_STRING   
```  
  
 ouvrez \\MCL\\MFC\\Include\\AfxRes.h et ajoutez cette directive include :  
  
```  
#include <winresrc.h>  
```