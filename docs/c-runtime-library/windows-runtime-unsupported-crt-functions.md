---
title: Fonctions CRT non prises en charge par Windows Runtime | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- unsupported CRT functions, Windows Runtime
- Windows Runtime, unsupported CRT functions
ms.assetid: bb8386d6-0ef8-460c-88d8-addff009b6f1
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f9fb74dbc28235f211f24d64ef125f2cccdafc7d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="windows-runtime-unsupported-crt-functions"></a>Fonctions CRT non prises en charge par Windows Runtime
Nombreuses sont les API Runtime C (CRT) qui ne peuvent pas être utilisées dans les applications du [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] qui s'exécutent dans Windows Runtime. Ces applications sont générées à l'aide de l'indicateur de compilateur /ZW. Pour obtenir la liste des fonctions CRT non prises en charge, consultez [Fonctions CRT non prises en charge par /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
 Toutes les API CRT sont décrites dans la section [Référence alphabétique des fonctions](../c-runtime-library/reference/crt-alphabetical-function-reference.md) de la documentation.  
  
## <a name="see-also"></a>Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)   
 [Référence alphabétique des fonctions](../c-runtime-library/reference/crt-alphabetical-function-reference.md)