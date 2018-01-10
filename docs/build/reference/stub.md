---
title: STUB | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: STUB
dev_langs: C++
helpviewer_keywords: STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 58430f8211f8859b65103b53d1f98a173c4635ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="stub"></a>STUB
Lorsqu’il est utilisé dans un fichier de définition de module qui génère un pilote de périphérique virtuel (VxD), vous permet de spécifier un nom de fichier qui contient une structure IMAGE_DOS_HEADER (définie dans WINNT. H) à utiliser dans le pilote de périphérique virtuel (VxD), au lieu de l’en-tête par défaut.  
  
```  
STUB:filename  
```  
  
## <a name="remarks"></a>Notes  
 Vous pouvez spécifier *nom de fichier* avec la [/STUB](../../build/reference/stub-ms-dos-stub-file-name.md) option de l’éditeur de liens.  
  
 STUB est valide dans un fichier de définition de module uniquement lors de la génération d’un pilote VxD.  
  
## <a name="see-also"></a>Voir aussi  
 [Règles s’appliquant aux instructions de définition de module](../../build/reference/rules-for-module-definition-statements.md)