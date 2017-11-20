---
title: VCPROFILE_PATH | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VCPROFILE_PATH
dev_langs: C++
helpviewer_keywords: VCPROFILE_PATH environment variable
ms.assetid: 25217aa4-7e86-4eba-854d-10b3c457e4df
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d5b4a2bbb46e906883f3f0c99c84d3b12cc0f104
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="vcprofilepath"></a>VCPROFILE_PATH
Spécifiez le répertoire pour créer des fichiers .pgc.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VCPROFILE_PATH=path  
```  
  
#### <a name="parameters"></a>Paramètres  
 `path`  
 Le chemin d’accès du répertoire dans les .pgc fichiers seront ajoutés.  
  
## <a name="remarks"></a>Remarques  
 Par défaut, les fichiers .pgc sont créés dans le même répertoire que le fichier binaire en cours de profilage.  Toutefois, si le chemin d’accès absolu du fichier binaire n’existe pas, ne peut être le cas lorsque vous exécutez des scénarios de profil sur une autre machine où le fichier binaire a été créé, vous pouvez définir `VCPROFILE_PATH` un chemin d’accès existant.  
  
## <a name="example"></a>Exemple  
  
```  
set VCPROFILE_PATH=c:\  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Variables d’environnement pour les optimisations guidées par profil](../../build/reference/environment-variables-for-profile-guided-optimizations.md)