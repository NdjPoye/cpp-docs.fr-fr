---
title: "Valeurs | Microsoft Docs"
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
  - "C"
ms.assetid: 24003f89-220f-4f93-be7a-b650c26157d7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Valeurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.1.2.5** Représentations et jeux de valeurs des différents types de nombres à virgule flottante  
  
 Le type **float** contient 32 bits : 1 pour le signe, 8 pour l'exposant et 23 pour la mantisse.  Sa plage est \+\/– 3.4E38 avec au moins 7 chiffres de précision.  
  
 Le type **double** contient 64 bits : 1 pour le signe, 11 pour l'exposant et 52 pour la mantisse.  Sa plage est \+\/– 1.7E308 avec au moins 15 chiffres de précision.  
  
 Le type **long double** contient 80 bits : 1 pour le signe, 15 pour l'exposant et 64 pour la mantisse.  Sa plage est \+\/– 1.2E4932 avec au moins 19 chiffres de précision.  Notez qu'avec le compilateur Microsoft C, la représentation du type **long double** est identique au type **double**.  
  
## Voir aussi  
 [Mathématiques à virgule flottante](../c-language/floating-point-math.md)