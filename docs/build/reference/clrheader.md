---
title: -CLRHEADER | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /CLRHEADER
dev_langs:
- C++
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 73f68c4f73d132254ea64d4b3b3b9f787f3a4b82
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="clrheader"></a>/CLRHEADER
```  
/CLRHEADER file  
```  
  
## <a name="remarks"></a>Notes  
 où :  
  
 `file`  
 Génération d’un fichier image avec [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="remarks"></a>Notes  
 /CLRHEADER affiche des informations sur les en-têtes .NET utilisés dans un programme managé. La sortie indique l’emplacement et la taille, en octets, de l’en-tête .NET et les sections dans l’en-tête.  
  
 Uniquement les [/HEADERS](../../build/reference/headers.md) (option DUMPBIN) est disponible pour les fichiers générés par le [/GL](../../build/reference/gl-whole-program-optimization.md) option du compilateur.  
  
 Si /CLRHEADER est utilisé sur un fichier qui a été compilé avec/CLR, il y aura un **clr Header :** section dans la sortie de dumpbin.  La valeur de **indicateurs** indique l’option /clr qui a été utilisée :  
  
-   0--/clr (image peut contenir du code natif).  
  
 Vous pouvez également vérifier par programme si une image a été créée pour le common language runtime.  Pour plus d’informations, consultez [Comment : déterminer si une Image est Native ou CLR](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md).  
  
 Le **/CLR : pure** et **/CLR : safe** options du compilateur sont déconseillées dans Visual Studio 2015 et sera supprimées dans une future version du compilateur. Le code qui doit être « pure » ou « sécurisée » doit être déplacée vers c#. 
  
## <a name="see-also"></a>Voir aussi  
 [DUMPBIN, options](../../build/reference/dumpbin-options.md)