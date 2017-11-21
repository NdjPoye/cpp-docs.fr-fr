---
title: "-/ERRORREPORT (signaler les erreurs internes de l’éditeur de liens) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ERRORREPORT
- VC.Project.VCLinkerTool.ErrorReporting
dev_langs: C++
helpviewer_keywords:
- /ERRORREPORT linker option
- ERRORREPORT linker option
- -ERRORREPORT linker option
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e6242457bb4da3e19700f5018b2a484bfa05630b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="errorreport-report-internal-linker-errors"></a>/ERRORREPORT (Signaler les erreurs internes de l'Éditeur de liens)
```  
/errorReport:[ none | prompt | queue | send ]  
```  
  
## <a name="remarks"></a>Remarques  
 Vous permet de signaler les erreurs internes du compilateur (ICE) directement à Microsoft.  
  
 L’option **/errorreport : send** tente d’envoyer automatiquement les informations d’erreur à Microsoft, mais réussite dépend des paramètres de Registre. Pour plus d’informations sur la façon de définir les valeurs appropriées dans le Registre, consultez [comment activer le rapport d’erreurs automatique dans les outils de ligne de commande de Visual Studio 2008](http://go.microsoft.com/fwlink/?LinkID=184695) sur le site Web MSDN.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le **propriétés de Configuration** dossier.  
  
3.  Cliquez sur le **l’éditeur de liens** dossier.  
  
4.  Cliquez sur le **avancé** page de propriétés.  
  
5.  Modifier la **rapport d’erreurs**propriété.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [/errorReport (signaler les erreurs du compilateur interne)](../../build/reference/errorreport-report-internal-compiler-errors.md)   
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)