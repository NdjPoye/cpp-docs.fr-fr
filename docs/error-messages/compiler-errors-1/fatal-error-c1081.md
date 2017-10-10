---
title: "Erreur irrécupérable C1081 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1081
dev_langs:
- C++
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 148e3e6035304eb155a478e5971defd9a0a55120
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1081"></a>Erreur irrécupérable C1081
'symbole' : nom de fichier trop long  
  
 La longueur d’un chemin d’accès de fichier dépasse `_MAX_PATH` (défini par STDLIB.h à 260 caractères). Raccourcissez le nom du fichier.  
  
 Si vous appelez CL.exe avec un nom de fichier court, le compilateur devrez peut-être générer un chemin d’accès complet. Par exemple, `cl -c myfile.cpp` peut entraîner le compilateur à générer :  
  
```  
D:\<very-long-directory-path>\myfile.cpp  
```
