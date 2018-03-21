---
title: VCPROFILE_PATH | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VCPROFILE_PATH
dev_langs:
- C++
helpviewer_keywords:
- VCPROFILE_PATH environment variable
ms.assetid: 25217aa4-7e86-4eba-854d-10b3c457e4df
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea682b70f4417ef49bfca530af5f12f21699a389
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
  
## <a name="remarks"></a>Notes  
 Par défaut, les fichiers .pgc sont créés dans le même répertoire que le fichier binaire en cours de profilage.  Toutefois, si le chemin d’accès absolu du fichier binaire n’existe pas, ne peut être le cas lorsque vous exécutez des scénarios de profil sur une autre machine où le fichier binaire a été créé, vous pouvez définir `VCPROFILE_PATH` un chemin d’accès existant.  
  
## <a name="example"></a>Exemple  
  
```  
set VCPROFILE_PATH=c:\  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Variables d’environnement pour les optimisations guidées par profil](../../build/reference/environment-variables-for-profile-guided-optimizations.md)