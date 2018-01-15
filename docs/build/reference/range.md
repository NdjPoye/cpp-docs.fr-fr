---
title: -PLAGE | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /RANGE
dev_langs: C++
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1ccca814a388a458513773247f79cecf87fcdeae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="range"></a>/RANGE
Modifie la sortie de dumpbin lorsqu’il est utilisé avec d’autres options de dumpbin, telles que /RAWDATA ou /DISASM.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/RANGE:vaMin[,vaMax]  
```  
  
## <a name="flags"></a>Indicateurs  
 **vaMin**  
 L’adresse virtuelle à laquelle vous voulez que l’opération de dumpbin pour commencer.  
  
 **vaMax** (facultatif)  
 L’adresse virtuelle à laquelle vous voulez que l’opération de dumpbin à la fin. Si non spécifié, dumpbin passera à la fin du fichier.  
  
## <a name="remarks"></a>Notes  
 Pour afficher les adresses virtuelles d’une image, utilisez le fichier de mappage de l’image (RVA + Base), la **/DISASM** ou **/HEADERS** possibilité de dumpbin ou de la fenêtre code machine dans le débogueur Visual Studio.  
  
## <a name="example"></a>Exemple  
 Dans cet exemple, **/plage** est utilisé pour modifier l’affichage de la **/disasm** option. Dans cet exemple, la valeur de départ est exprimée en nombre décimal et la valeur de fin est spécifiée comme un nombre hexadécimal.  
  
```  
dumpbin /disasm /range:4219334,0x004061CD t.exe  
```  
  
## <a name="see-also"></a>Voir aussi  
 [DUMPBIN, options](../../build/reference/dumpbin-options.md)