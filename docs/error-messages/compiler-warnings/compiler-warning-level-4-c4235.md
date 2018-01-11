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
ms.workload: cplusplus
ms.openlocfilehash: b0fea028932a48b9c7ee1a677a3e6dc8078edc35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4235"></a>Avertissement du compilateur (niveau 4) C4235
extension non standard utilisée : ' mot_clé ' non pris en charge sur cette architecture  
  
 Le compilateur ne prend pas en charge le mot clé que vous avez utilisé.  
  
 Cet avertissement est automatiquement promu en une erreur. Si vous souhaitez modifier ce comportement, utilisez [#pragma warning](../../preprocessor/warning.md). Par exemple, pour transformer l’avertissement C4235 en un avertissement de niveau 2, utilisez la ligne suivante de code  
  
```  
#pragma warning(2:4235)  
```  
  
 dans votre fichier de code source.