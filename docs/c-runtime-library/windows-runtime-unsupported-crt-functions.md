---
title: Fonctions CRT non prises en charge par Windows Runtime | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- unsupported CRT functions, Windows Runtime
- Windows Runtime, unsupported CRT functions
ms.assetid: bb8386d6-0ef8-460c-88d8-addff009b6f1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a2f6b06b45da502e3eba898f2907042afeca65c2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="windows-runtime-unsupported-crt-functions"></a>Fonctions CRT non prises en charge par Windows Runtime
De nombreuses API Runtime C (CRT) ne peuvent pas être utilisées dans les applications de plateforme Windows universelle qui s'exécutent dans Windows Runtime. Ces applications sont générées à l'aide de l'indicateur de compilateur /ZW. Pour obtenir la liste des fonctions CRT non prises en charge, consultez [Fonctions CRT non prises en charge par /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
 Toutes les API CRT sont décrites dans la section [Référence alphabétique des fonctions](../c-runtime-library/reference/crt-alphabetical-function-reference.md) de la documentation.  
  
## <a name="see-also"></a>Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)   
 [Référence alphabétique des fonctions](../c-runtime-library/reference/crt-alphabetical-function-reference.md)