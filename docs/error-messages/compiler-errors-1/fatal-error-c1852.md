---
title: Erreur irrécupérable C1852 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
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
ms.workload:
- cplusplus
ms.openlocfilehash: 33dfff145ce504c5c445299a33b529fe54b601e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1852"></a>Erreur irrécupérable C1852
'nom_fichier' n’est pas un fichier d’en-tête précompilé valide  
  
 Le fichier n’est pas un en-tête précompilé.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Fichier non valide spécifié avec **/Yu** ou **#pragma hdrstop**.  
  
2.  Le compilateur suppose que l’extension de fichier est .pch, sauf indication contraire de votre part.