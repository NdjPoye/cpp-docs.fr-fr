---
title: Compilateur avertissement (niveau 1) C4612 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4612
dev_langs: C++
helpviewer_keywords: C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1a2d5ddc76271df594c2bd5b2ae1707933510338
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4612"></a>Avertissement du compilateur (niveau 1) C4612
erreur dans le nom de fichier Include  
  
 Cet avertissement se produit avec **#pragma include_alias** quand un nom de fichier est incorrect ou manquant.  
  
 Les arguments de l’instruction **#pragma include_alias** peuvent utiliser les guillemets de (**"***nom_fichier***"**) ou les crochets pointus de (**\<***nom_fichier***>**), mais les deux doivent utiliser la même forme.  
  
## <a name="example"></a>Exemple  
  
```  
// C4612.cpp  
// compile with: /W1 /LD  
#pragma include_alias("StandardIO", <stdio.h>) // C4612  
```