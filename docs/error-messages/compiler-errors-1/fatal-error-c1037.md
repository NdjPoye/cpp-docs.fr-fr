---
title: "Erreur irr&#233;cup&#233;rable C1037 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1037"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1037"
ms.assetid: 79103bca-ccfb-42e7-aef9-9b90c15b162f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1037
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d’ouvrir le fichier objet 'nom\_fichier'  
  
 Le fichier objet spécifié par [\/Fo](../../build/reference/fo-object-file-name.md) ne peut pas être ouvert.  
  
### Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Nom de fichier non valide.  
  
2.  Mémoire insuffisante pour ouvrir le fichier.  
  
3.  Un autre processus utilise le fichier.  
  
4.  Un fichier en lecture seule porte le même nom.  
  
 Dans Visual C\+\+ .NET \(version 1300 du compilateur\), il existe un bogue qui exige que les paramètres régionaux utilisateur soient définis correctement quand le nom de fichier \(ou le chemin du répertoire du nom de fichier\) contient des caractères MBCS. Le fait de définir les paramètres régionaux système ne suffit pas ; vous devez configurer les paramètres régionaux utilisateur pour traiter les caractères MBCS.