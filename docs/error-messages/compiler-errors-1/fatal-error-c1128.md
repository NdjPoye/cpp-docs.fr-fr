---
title: "Erreur irr&#233;cup&#233;rable C1128 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1128"
ms.assetid: 6f9580fd-ecef-48be-9780-dcf666704279
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Erreur irr&#233;cup&#233;rable C1128
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le nombre de sections a dépassé la limite du format de fichier objet : compilez avec \/bigobj  
  
 Un fichier .obj a dépassé le nombre de sections autorisé, une limitation du format de fichier objet COFF.  
  
 Cette limitation du nombre de sections peut être dépassée lors de l'utilisation de [\/Gy](../../build/reference/gy-enable-function-level-linking.md) et d'une version Debug ; en présence de **\/Gy**, les fonctions passent dans leurs propres sections COMDAT.  Dans une version Debug, chaque fonction COMDAT comporte une section d'informations de débogage.  
  
 L'erreur C1128 peut également être causée par un trop grand nombre de fonctions inline.  
  
 Pour corriger cette erreur, divisez votre fichier source en plusieurs fichiers de code source et compilez sans **\/Gy** ou compilez avec[\/bigobj \(Augmenter le nombre de sections dans le fichier .obj\)](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md).  Si vous ne compilez pas avec **\/Gy**, vous devez spécifier les optimisations individuellement, car **\/O2** et **\/O1** impliquent toutes les deux **\/Gy**.  
  
 Dans la mesure du possible, compilez sans informations de débogage.  
  
 Il est aussi possible que vous ayez besoin de disposer d'instanciations spécifiques de modèles dans des fichiers de code source séparés, plutôt que de demander au compilateur de les émettre.  
  
 Lorsque vous convertissez du code, l'erreur C1128 apparaîtra probablement d'abord lors de l'utilisation du compilateur x64, et beaucoup plus tard avec le compilateur x86. x64 comportera au moins 4 sections associées à chaque fonction compilée avec **\/Gy** ou inlinée à partir de modèles ou d'une classe inline : code, pdata, informations de débogage, et éventuellement xdata.  Le compilateur X86 ne comprend pas pdata.