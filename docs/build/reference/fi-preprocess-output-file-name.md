---
title: "-Fi (Prétraiter le nom de fichier de sortie) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Fi
dev_langs: C++
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9bc3076a529984358aed16902f509ceb01423f9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fi-preprocess-output-file-name"></a>/Fi (prétraiter le nom du fichier de sortie)
Spécifie le nom du fichier de sortie dans lequel le [/P (Prétraiter dans un fichier)](../../build/reference/p-preprocess-to-a-file.md) option du compilateur écrit la sortie prétraitée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/Fipathname  
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`pathname`|Le nom et le chemin d’accès du fichier de sortie produits par le **/P** option du compilateur.|  
  
## <a name="remarks"></a>Notes  
 Utilisez le **/Fi** option du compilateur en combinaison avec la **/P** option du compilateur.  
  
 Si vous spécifiez uniquement un chemin d’accès pour le `pathname` paramètre, le nom de base du fichier source est utilisé comme nom de base du fichier de sortie prétraité. Le `pathname` paramètre ne nécessite pas une extension de nom de fichier particulier. Toutefois, une extension de « .i » est utilisée si vous ne spécifiez pas une extension de nom de fichier.  
  
## <a name="example"></a>Exemple  
 La ligne de commande suivante prétraite PROGRAM.cpp, conserve les commentaires, ajoute [#line](../../preprocessor/hash-line-directive-c-cpp.md) directives et écrit le résultat dans le fichier MYPROCESS.i.  
  
```  
CL /P /FiMYPROCESS.I PROGRAM.CPP  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [/P (Prétraiter jusqu'à un fichier)](../../build/reference/p-preprocess-to-a-file.md)   
 [Spécification du nom de chemin](../../build/reference/specifying-the-pathname.md)