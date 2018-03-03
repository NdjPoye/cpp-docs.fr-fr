---
title: Avertissement BSCMAKE BK4504 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- BK4504
dev_langs:
- C++
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 58a59b3141a8d7051aa7ece1bcb71dd960fabb18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-warning-bk4504"></a>Avertissement BSCMAKE BK4504
fichier contient trop de références ; en ignorant les références ultérieures provenant de cette source  
  
 Le fichier .cpp contient plus de 64 000 références des symboles. Lorsque BSCMAKE a rencontré des références 64 000 dans un fichier, il ignore toutes les références supplémentaires.  
  
 Pour corriger le problème, fractionnez le fichier en deux ou plusieurs fichiers, chacun d'entre eux ayant moins de 64 000 références de symboles, ou utilisent la `#pragma component(browser)` directive de préprocesseur limite les symboles qui sont générés pour les références particuliers. Pour plus d’informations, consultez [composant](../../preprocessor/component.md).