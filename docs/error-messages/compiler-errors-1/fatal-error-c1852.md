---
title: "Erreur irrécupérable C1852 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1852
dev_langs:
- C++
helpviewer_keywords:
- C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: f3e2b190ed3ec30c429bded2b6b695e1838cd078
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1852"></a>Erreur irrécupérable C1852
'nom_fichier' n’est pas un fichier d’en-tête précompilé valide  
  
 Le fichier n’est pas un en-tête précompilé.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Fichier non valide spécifié avec **/Yu** ou **#pragma hdrstop**.  
  
2.  Le compilateur suppose que l’extension de fichier est .pch, sauf indication contraire de votre part.
