---
title: Compilateur avertissement (niveau 4) C4235 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4235
dev_langs: C++
helpviewer_keywords: C4235
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f4266a2aae53254bbb7c2a043ccf3240d69cc63a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4235"></a>Avertissement du compilateur (niveau 4) C4235
extension non standard utilisée : ' mot_clé ' non pris en charge sur cette architecture  
  
 Le compilateur ne prend pas en charge le mot clé que vous avez utilisé.  
  
 Cet avertissement est automatiquement promu en une erreur. Si vous souhaitez modifier ce comportement, utilisez [#pragma warning](../../preprocessor/warning.md). Par exemple, pour transformer l’avertissement C4235 en un avertissement de niveau 2, utilisez la ligne suivante de code  
  
```  
#pragma warning(2:4235)  
```  
  
 dans votre fichier de code source.