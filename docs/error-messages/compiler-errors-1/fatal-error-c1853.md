---
title: "Erreur irr&#233;cup&#233;rable C1853 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1853"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1853"
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Erreur irr&#233;cup&#233;rable C1853
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le fichier d'en\-tête précompilé 'NomFichier' est issu d'une version antérieure du compilateur, ou l'en\-tête précompilé est en C\+\+ et vous l'utilisez en C \(ou inversement\)  
  
 Causes possibles :  
  
-   L'en\-tête précompilé a été compilé avec une version précédente du compilateur.  Essayez de recompiler l'en\-tête avec le compilateur actuel.  
  
-   L'en\-tête précompilé est en C\+\+ et vous l'utilisez en C.  Essayez de recompiler l'en\-tête pour l'utiliser avec C en spécifiant une des options de compilateur [\/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) ou en remplaçant le suffixe du fichier source par "c".  Pour plus d'informations, consultez [Deux méthodes au choix pour la précompilation du code](../../build/reference/two-choices-for-precompiling-code.md).