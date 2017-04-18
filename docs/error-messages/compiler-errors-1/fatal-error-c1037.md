---
title: "Erreur irrécupérable C1037 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1037
dev_langs:
- C++
helpviewer_keywords:
- C1037
ms.assetid: 79103bca-ccfb-42e7-aef9-9b90c15b162f
caps.latest.revision: 7
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
ms.openlocfilehash: 892ce10f7d19266ce45d559ce35bc82946887c52
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1037"></a>Erreur irrécupérable C1037
impossible d’ouvrir le fichier objet 'nom_fichier'  
  
 Le fichier objet spécifié par [/Fo](../../build/reference/fo-object-file-name.md) ne peut pas être ouvert.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Nom de fichier non valide.  
  
2.  Mémoire insuffisante pour ouvrir le fichier.  
  
3.  Un autre processus utilise le fichier.  
  
4.  Un fichier en lecture seule porte le même nom.  
  
 Dans Visual C++ .NET (version 1300 du compilateur), il existe un bogue qui exige que les paramètres régionaux utilisateur soient définis correctement quand le nom de fichier (ou le chemin du répertoire du nom de fichier) contient des caractères MBCS. Le fait de définir les paramètres régionaux système ne suffit pas ; vous devez configurer les paramètres régionaux utilisateur pour traiter les caractères MBCS.
