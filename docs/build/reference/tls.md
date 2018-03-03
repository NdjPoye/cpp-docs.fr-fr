---
title: -TLS | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /TLS
dev_langs:
- C++
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5adf246e343a16abebdc584589e9633b195444ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="tls"></a>/TLS
Affiche la structure IMAGE_TLS_DIRECTORY à partir d’un fichier exécutable.  
  
## <a name="remarks"></a>Notes  
 /TLS affiche les champs de la structure TLS ainsi que les adresses des fonctions de rappel TLS.  
  
 Si un programme n’utilise pas le stockage local des threads, son image ne contient pas de structure TLS.  Consultez [thread](../../cpp/thread.md) pour plus d’informations.  
  
 IMAGE_TLS_DIRECTORY est défini dans winnt.h.  
  
## <a name="see-also"></a>Voir aussi  
 [DUMPBIN, options](../../build/reference/dumpbin-options.md)