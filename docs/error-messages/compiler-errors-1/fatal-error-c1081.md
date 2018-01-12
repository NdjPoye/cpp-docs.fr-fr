---
title: "Erreur irrécupérable C1081 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1081
dev_langs: C++
helpviewer_keywords: C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8bac4aaf0d4aebcbc34f74b6ccb91170fd4224e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1081"></a>Erreur irrécupérable C1081
'symbole' : nom de fichier trop long  
  
 La longueur d’un chemin d’accès de fichier dépasse `_MAX_PATH` (défini par STDLIB.h à 260 caractères). Raccourcissez le nom du fichier.  
  
 Si vous appelez CL.exe avec un nom de fichier court, le compilateur devrez peut-être générer un chemin d’accès complet. Par exemple, `cl -c myfile.cpp` peut entraîner le compilateur à générer :  
  
```  
D:\<very-long-directory-path>\myfile.cpp  
```