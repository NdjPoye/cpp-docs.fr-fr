---
title: -PROFIL (profileur des outils performances) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.Profile
dev_langs: C++
helpviewer_keywords:
- -PROFILE linker option
- /PROFILE linker option
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 54aff4c81b0bff9fcd6727333ee7d17c76564c71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE (Profileur des outils d'analyse des performances)
Génère un fichier de sortie utilisable avec le profileur Outils d’analyse des performances.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/PROFILE  
```  
  
## <a name="remarks"></a>Notes  
 /Profile implique les options de l’éditeur de liens suivantes :  
  
-   [/ OPT : REF](../../build/reference/opt-optimizations.md)  
  
-   / OPT : NOICF  
  
-   [/ INCREMENTAL : NO](../../build/reference/incremental-link-incrementally.md)  
  
-   [/ FIXE : NO](../../build/reference/fixed-fixed-base-address.md)  
  
 /Profile indique à l’éditeur de liens générer une section de réadressage dans l’image de programme.  Une section de réadressage permet au profileur de transformer l’image de programme pour obtenir des données de profil.  
  
 **/ PROFIL** n’est disponible uniquement dans les versions entreprise (développement en équipe).  Pour plus d’informations sur PREfast, consultez [analyse du Code pour C/C++ Overview](/visualstudio/code-quality/code-analysis-for-c-cpp-overview).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Développez le **propriétés de Configuration** nœud.  
  
3.  Développez le **l’éditeur de liens** nœud.  
  
4.  Sélectionnez le **avancé** page de propriétés.  
  
5.  Modifier la **profil** propriété.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)