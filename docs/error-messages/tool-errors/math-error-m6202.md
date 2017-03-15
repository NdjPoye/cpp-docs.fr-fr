---
title: "Erreur math&#233;matique M6202 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "M6202"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "M6202"
ms.assetid: 4d17045f-c6dc-4705-9512-e9af12c35fb4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur math&#233;matique M6202
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : \_SING error  
  
 Un argument de la fonction était une valeur de singularité pour cette fonction.  Cette fonction n'est pas définie pour cet argument.  
  
 Cette erreur appelle la fonction `_matherr` avec le nom de la fonction, ses arguments et le type d'erreur.  Vous pouvez réécrire la fonction `_matherr` pour personnaliser la gestion de certaines erreurs mathématiques à virgule flottante survenant au moment de l'exécution.