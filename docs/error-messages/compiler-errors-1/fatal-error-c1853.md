---
title: "Erreur irrécupérable C1853 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1853
dev_langs: C++
helpviewer_keywords: C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 23b5302428fc216a8349e8cf022c184caa57202c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1853"></a>Erreur irrécupérable C1853
  
> '*nom de fichier*' fichier d’en-tête précompilé est d’une version antérieure du compilateur, ou l’en-tête précompilé est en C++ et vous l’utilisez en C (ou inversement)  
  
Causes possibles :  
  
-   L’en-tête précompilé a été compilé avec une version précédente de compilateur. Essayez de recompiler l’en-tête avec le compilateur actuel.  
  
-   L’en-tête précompilé est en C++ et vous l’utilisez de réessayez C. recompiler l’en-tête pour une utilisation avec C en spécifiant l’une de le [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) options du compilateur, ou en remplaçant le suffixe du fichier source par « c ». Pour plus d’informations, consultez [deux possibilités pour précompiler le Code](../../build/reference/creating-precompiled-header-files.md#two-choices-for-precompiling-code).