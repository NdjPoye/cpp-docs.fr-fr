---
title: composant | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.component
- component_CPP
dev_langs:
- C++
helpviewer_keywords:
- component pragma
- pragmas, component
ms.assetid: 7b66355e-3201-4c14-8190-f4a2a81a604a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3edb2f68b479eeadca777e0707dd96e148d13fe8
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="component"></a>component
Contrôle la collecte des informations de consultation ou les informations sur les dépendances à partir des fichiers sources.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      #pragma component( browser, { on | off }[, references [, name ]] )  
#pragma component( minrebuild, on | off )  
#pragma component( mintypeinfo, on | off )  
```  
  
## <a name="remarks"></a>Notes  
  
## <a name="browser"></a>Visiteur  
 Vous pouvez désactiver ou activer la collecte, et spécifier des noms particuliers à ignorer lors de la collecte d'informations.  
  
 L’utilisation de l’activation et de la désactivation contrôle la collection des informations de consultation à partir du pragma. Exemple :  
  
```  
#pragma component(browser, off)  
```  
  
 arrête la collecte d'informations de consultation par le compilateur.  
  
> [!NOTE]
>  Pour activer la collecte des informations de consultation avec ce pragma, [des informations de consultation doivent d’abord être activées](../build/reference/building-browse-information-files-overview.md).  
  
 Le **références** option peut être utilisée avec ou sans le *nom* argument. À l’aide de **références** sans *nom* Active ou désactive la collecte de références (les autres informations de consultation continuent à être collectées). Exemple :  
  
```  
#pragma component(browser, off, references)  
```  
  
 arrête la collecte d'informations de référence par le compilateur.  
  
 À l’aide de **références** avec *nom* et **hors** empêche les références à *nom* d’apparaître dans la fenêtre d’informations de navigation. Utilisez cette syntaxe pour ignorer les noms et les types qui ne vous intéressent pas afin de réduire la taille des fichiers d'informations de consultation. Exemple :  
  
```  
#pragma component(browser, off, references, DWORD)  
```  
  
 ignore les références à **DWORD** à partir de là. Vous pouvez réactiver la collecte de références à `DWORD` à l’aide **sur**:  
  
```  
#pragma component(browser, on, references, DWORD)  
```  
  
 C’est la seule façon de reprendre la collecte des références à *nom*; vous devez activer explicitement sur n’importe quel *nom* que vous avez désactivé.  
  
 Pour empêcher le préprocesseur de développer *nom* (par exemple de développer **NULL** à **0**), placez des guillemets autour :  
  
```  
#pragma component(browser, off, references, "NULL")  
```  
  
## <a name="minimal-rebuild"></a>Régénération minimale  
 La fonctionnalité de régénération minimale Visual C++ exige que le compilateur crée et stocke des informations sur les dépendances de classe C++, ce qui occupe de l’espace sur le disque. Pour économiser l’espace disque, vous pouvez utiliser `#pragma component( minrebuild, off )` chaque fois que vous n’avez pas besoin de collecter des informations de dépendance, par exemple, dans les fichiers d’en-tête qui ne changent pas. Insérer `#pragma component(minrebuild, on)` après les classes qui ne changent pas pour activer la collection de dépendances.  
  
## <a name="reduce-type-information"></a>Réduction des informations de type  
 Le **mintypeinfo** option permet de réduire les informations de débogage pour la région spécifiée. Le volume de ces informations est considérable et a un impact sur les fichiers .pdb et .obj. Vous ne pouvez pas déboguer des classes et des structures dans la zone mintypeinfo. L'utilisation de l'option mintypeinfo peut être utile pour éviter l'avertissement suivant :  
  
```  
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information  
```  
  
 Pour plus d’informations, consultez la [activer la régénération minimale](../build/reference/gm-enable-minimal-rebuild.md) (/ Gm) option du compilateur.  
  
## <a name="see-also"></a>Voir aussi  
 [Directives pragma et mot clé _Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)