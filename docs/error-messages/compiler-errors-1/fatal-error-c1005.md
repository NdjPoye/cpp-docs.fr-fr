---
title: "Erreur irrécupérable C1005 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1005
dev_langs:
- C++
helpviewer_keywords:
- C1005
ms.assetid: 150daf8e-a38a-4669-9c1a-a05b5a1f65ef
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e558112619e5cbefd641e7906df941d0869ceddb
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1005"></a>Erreur irrécupérable C1005
chaîne trop grande pour la mémoire tampon  
  
 Une chaîne dans un fichier intermédiaire du compilateur a entraîné un dépassement de mémoire tampon.  
  
 Vous pouvez obtenir cette erreur quand le paramètre que vous passez aux options de compilateur [/Fd](../../build/reference/fd-program-database-file-name.md) ou [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) est supérieur à 256 octets.
