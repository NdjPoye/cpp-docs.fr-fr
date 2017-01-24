---
title: "Erreur d’analyse de la documentation XML&#160;: la balise de d&#233;but &#39;&lt;balise&gt;&#39; n’a pas de balise de fin correspondante | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc42316"
  - "BC42316"
helpviewer_keywords: 
  - "BC42316"
ms.assetid: 45b68176-ebf6-43af-820e-6801aabb6c57
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Erreur d’analyse de la documentation XML&#160;: la balise de d&#233;but &#39;&lt;balise&gt;&#39; n’a pas de balise de fin correspondante
Erreur d’analyse de la documentation XML : la balise de début \<balise\> n’a pas de balise de fin correspondante. Le commentaire XML sera ignoré.  
  
 Le commentaire XML contient une balise de début, mais ne contient pas de balise de fin correspondante.  
  
 **ID d’erreur :** BC42316  
  
### Pour corriger cette erreur  
  
-   Ajoutez une balise de fin qui correspond à la balise de début.  
  
     — ou —  
  
-   Si la balise ne contient aucun texte interne, par exemple [\<seealso\>](../Topic/%3Cseealso%3E%20\(Visual%20Basic\).md), spécifiez une barre oblique avant le crochet fermant.  
  
## Voir aussi  
 [XML Comment Tags](../Topic/Recommended%20XML%20Tags%20for%20Documentation%20Comments%20\(Visual%20Basic\).md)   
 [Documenting Your Code with XML](../Topic/Documenting%20Your%20Code%20with%20XML%20\(Visual%20Basic\).md)