---
title: "Erreur irrécupérable C1905 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1905
dev_langs:
- C++
helpviewer_keywords:
- C1905
ms.assetid: fefc6769-477f-45a2-9878-6f0a5f42472c
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9d1662b05764500d0ac6a96119f865294cac260b
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1905"></a>Erreur irrécupérable C1905
Front-end et back end non compatibles (doivent cibler le même processeur)  
  
 Cette erreur se produit quand un fichier .obj est généré par un compilateur frontal (C1.dll) qui cible un processeur, tel que x86, ARM ou [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], mais qui est lu par un compilateur principal (C2.dll) qui cible un processeur différent.  
  
 Pour résoudre ce problème, assurez-vous d'utiliser un compilateur frontal et un compilateur principal qui correspondent. Il s'agit du paramétrage par défaut pour les projets créés dans Visual Studio. Cette erreur peut se produire si vous avez modifié le fichier projet et utilisé des chemins d'accès aux outils de compilateur différents. Si vous n'avez pas spécifiquement défini de chemin d'accès pour les outils du compilateur, cette erreur peut survenir si votre installation de Visual Studio est endommagée. Par exemple, vous pouvez avoir copié les fichiers .dll du compilateur d'un emplacement à un autre. Utilisez **programmes et fonctionnalités** dans le panneau de configuration Windows pour réparer ou réinstaller Visual Studio.
