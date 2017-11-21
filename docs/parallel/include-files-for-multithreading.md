---
title: Les fichiers Include pour le Multithreading | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- threading [C++], include files
- include files, multithreading
- multithreading [C++], include files
ms.assetid: 98d764f9-71f4-4da5-8f3a-8d2d26e96799
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bcc8282680588585335eaa2c876128d2c2cf23a3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="include-files-for-multithreading"></a>Fichiers include pour le multithreading
Fichiers include standard déclarent les fonctions de bibliothèque Runtime C implémentées dans les bibliothèques. Si vous utilisez la [optimisation complète](../build/reference/ox-full-optimization.md) (/ Ox) ou [appel fastcall](../build/reference/gd-gr-gv-gz-calling-convention.md) (/ Gr) option, le compilateur suppose que toutes les fonctions doivent être appelées à l’aide de la convention d’appel de Registre. Les fonctions de la bibliothèque Runtime sont compilées à l’aide de la convention d’appel C, et les déclarations dans les fichiers include standard indiquent au compilateur de générer des références externes correctes à ces fonctions.  
  
## <a name="see-also"></a>Voir aussi  
 [Multithreading à l’aide de C et de Win32](../parallel/multithreading-with-c-and-win32.md)