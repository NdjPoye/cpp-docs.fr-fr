---
title: Compilateur avertissement (niveau 4) C4611 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4611
dev_langs: C++
helpviewer_keywords: C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8f2ed128d37ff4c09247097d771bc62a97f6e757
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4611"></a>Avertissement du compilateur (niveau 4) C4611
interaction entre 'fonction' et la destruction d’objets C++ n’est pas portable  
  
 Sur certaines plateformes, les fonctions qui incluent **catch** peut prend pas en charge la sémantique de destruction lorsque hors de portée d’objet C++.  
  
 Pour éviter un comportement inattendu, évitez d’utiliser **catch** dans les fonctions qui possèdent des constructeurs et destructeurs.  
  
 Cet avertissement est émis uniquement une seule fois ; consultez [(pragma) warning](../../preprocessor/warning.md).