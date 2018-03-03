---
title: "Erreur irrécupérable C1128 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1128
dev_langs:
- C++
helpviewer_keywords:
- C1128
ms.assetid: 6f9580fd-ecef-48be-9780-dcf666704279
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 22b53914fba8ab5d5c31d8f7ed0a2e3db52aad5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1128"></a>Erreur irrécupérable C1128
nombre de sections a dépassé la limite du format de fichier objet : compilez avec /bigobj  
  
 Un fichier .obj a dépassé le nombre de sections autorisé, une limitation du format de fichier objet COFF.  
  
 Limitation du nombre de cette section peut être le résultat de l’utilisation de [/Gy](../../build/reference/gy-enable-function-level-linking.md) et une version debug ; **/Gy** , les fonctions passent dans leurs propres sections COMDAT. Dans une version debug, il existe une section d’informations de débogage pour chaque fonction COMDAT.  
  
 C1128 peut également être provoquée lorsqu’il y a trop de fonctions inline.  
  
 Pour corriger cette erreur, divisez votre fichier source en plusieurs fichiers de code source, compilez sans **/Gy**, ou compilez avec [/bigobj (augmenter le nombre de Sections dans. Fichier obj)](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md).  Si vous ne compilez pas avec **/Gy**, vous devez spécifier les optimisations individuellement, étant donné que **/O2** et **/O1** impliquent toutes les deux **/Gy**.  
  
 Dans la mesure du possible, compilez sans informations de débogage.  
  
 Vous devez également disposer d’instanciations spécifiques de modèles dans les fichiers de code source distinct, plutôt que de laisser le compilateur les émettre.  
  
 Lors du portage du code, C1128 probablement apparaît en premier lorsque vous utilisez la x64 compilateur et beaucoup plus tard avec la x86 compilateur. x64 aura au moins 4 sections associées à chaque fonction compilée avec **/Gy** ou marquée comme inline à partir de modèles ou d’une classe inline : code, pdata et les informations de débogage et éventuellement xdata.  X86 ne comprend pas pdata.