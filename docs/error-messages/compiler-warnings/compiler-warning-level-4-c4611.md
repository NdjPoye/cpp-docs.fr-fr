---
title: Compilateur avertissement (niveau 4) C4611 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4611
dev_langs:
- C++
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3020cf7d115b735141b81e9007ac7fd027ed8674
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4611"></a>Avertissement du compilateur (niveau 4) C4611
interaction entre 'fonction' et la destruction d’objets C++ n’est pas portable  
  
 Sur certaines plateformes, les fonctions qui incluent **catch** peut prend pas en charge la sémantique de destruction lorsque hors de portée d’objet C++.  
  
 Pour éviter un comportement inattendu, évitez d’utiliser **catch** dans les fonctions qui possèdent des constructeurs et destructeurs.  
  
 Cet avertissement est émis uniquement une seule fois ; consultez [(pragma) warning](../../preprocessor/warning.md).