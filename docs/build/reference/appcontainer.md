---
title: -APPCONTAINER | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /APPCONTAINER
dev_langs: C++
helpviewer_keywords:
- APPCONTAINER editbin option
- -APPCONTAINER editbin option
- /APPCONTAINER editbin option
ms.assetid: 0ca4f1ec-c8de-4a37-b3e2-deda7af0bb88
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 62b23ed04783971bf37442237e4db770b7427a8d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="appcontainer"></a>/APPCONTAINER
Marque un fichier exécutable qui doit s’exécuter dans un conteneur d’application, par exemple une [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] ou une application Windows universelle.  
  
```  
  
/APPCONTAINER[:NO]  
```  
  
## <a name="remarks"></a>Remarques  
 Un fichier exécutable dont l’option **/APPCONTAINER** est définie ne peut être exécuté que dans un conteneur d’application, ce qui correspond à l’environnement d’isolation des processus introduit dans Windows 8. Pour [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] et les applications Windows universelles, cette option doit être définie.  
  
## <a name="see-also"></a>Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)   
 [Qu’est une application Windows universelle ?](http://go.microsoft.com/fwlink/p/?LinkID=522074)