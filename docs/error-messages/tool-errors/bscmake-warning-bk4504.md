---
title: Avertissement BSCMAKE BK4504 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK4504
dev_langs: C++
helpviewer_keywords: BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f7f6d854fbd74d9ca05ba6797bbd57db52b7a70e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="bscmake-warning-bk4504"></a>Avertissement BSCMAKE BK4504
fichier contient trop de références ; en ignorant les références ultérieures provenant de cette source  
  
 Le fichier .cpp contient plus de 64 000 références des symboles. Lorsque BSCMAKE a rencontré des références 64 000 dans un fichier, il ignore toutes les références supplémentaires.  
  
 Pour corriger le problème, fractionnez le fichier en deux ou plusieurs fichiers, chacun d'entre eux ayant moins de 64 000 références de symboles, ou utilisent la `#pragma component(browser)` directive de préprocesseur limite les symboles qui sont générés pour les références particuliers. Pour plus d’informations, consultez [composant](../../preprocessor/component.md).