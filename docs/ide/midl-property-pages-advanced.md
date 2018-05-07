---
title: 'Pages de propriétés MIDL : Avancé | Documents Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCMidlTool.ErrorCheckBounds
- VC.Project.VCMidlTool.ErrorCheckStubData
- VC.Project.VCMidlTool.ErrorCheckAllocations
- VC.Project.VCMidlTool.CPreprocessOptions
- VC.Project.VCMidlTool.UndefinePreprocessorDefinitions
- VC.Project.VCMidlTool.EnableErrorChecks
- VC.Project.VCMidlTool.RedirectOutputAndErrors
- VC.Project.VCMidlTool.ErrorCheckEnumRange
- VC.Project.VCMidlTool.StructMemberAlignment
- VC.Project.VCMidlTool.ErrorCheckRefPointers
- VC.Project.VCMidlTool.ValidateParameters
dev_langs:
- C++
helpviewer_keywords:
- MIDL, property pages
ms.assetid: d1c92e01-f403-4ed6-ab45-4043a3c9c6bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5f87518c23848cea91a3e3c48361aa0a63fa88a2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="midl-property-pages-advanced"></a>Pages de propriétés MIDL : Avancé
Le **avancé** page de propriétés dans le **MIDL** dossier spécifie les options de compilateur MIDL suivantes :  
  
-   Activer la vérification des erreurs ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Vérifie les Allocations ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Vérifier les limites ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Vérification de la plage Enum ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Vérifier les pointeurs de référence ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Vérifier les données Stub ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Valider les paramètres ([/ robust](http://msdn.microsoft.com/library/windows/desktop/aa367363)) *  
  
-   Alignement des membres de struct ([/Zp](http://msdn.microsoft.com/library/windows/desktop/aa367388))  
  
-   Rediriger la sortie ([/o](http://msdn.microsoft.com/library/windows/desktop/aa367351))  
  
-   Options de préprocesseur C ([/cpp_opt](http://msdn.microsoft.com/library/windows/desktop/aa367318))  
  
-   Définitions de préprocesseur non définies ([/U](http://msdn.microsoft.com/library/windows/desktop/aa367373))  
  
 \* / fiable est utilisable uniquement lors de la génération pour Windows 2000 ou un ordinateur plus loin. Si vous générez un projet ATL et que vous souhaitez utiliser / robust, modifiez cette ligne dans le fichier dlldatax.c :  
  
```  
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM  
to   
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM  
```  
  
 Pour plus d’informations sur l’accès à la **avancé** page de propriétés dans le **MIDL** dossier, consultez [utilisation des propriétés de projet](../ide/working-with-project-properties.md).  
  
 Pour plus d’informations sur l’accès par programme aux options MIDL des projets C++, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>.  
  
## <a name="see-also"></a>Voir aussi  
 [MIDL, page de propriétés](../ide/midl-property-pages.md)