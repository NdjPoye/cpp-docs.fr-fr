---
title: "-Qpar-report (niveau de Reporting PARALLÉLISEUR automatique) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 562673b9-02da-4bf8-bb64-70bc25ef4651
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 96dff858d068f9d9bf9c6c47e1f444603c2a5729
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="qpar-report-auto-parallelizer-reporting-level"></a>/Qpar-report (Niveau de rapport du paralléliseur automatique)
Active la fonctionnalité de création de rapports du compilateur [PARALLÉLISEUR](../../parallel/auto-parallelization-and-auto-vectorization.md) et spécifie le niveau des messages d’information pour la sortie pendant la compilation.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/Qpar-report:{1}{2}  
```  
  
## <a name="remarks"></a>Remarques  
 **/ Qpar-report : 1**  
 Génère un message d'information pour les boucles parallélisées.  
  
 **/ Qpar-report : 2**  
 Génère un message d'information pour les boucles parallélisées et non parallélisées, ainsi qu'un code motif.  
  
 Les messages sont signalés à stdout. Si aucun message d'information n'est signalé, cela signifie que le code ne contient pas de boucle ou que le niveau de rapport n'a pas été défini pour signaler les boucles non parallélisées. Pour plus d’informations sur les codes motifs et les messages, consultez [Messages du Vectoriseur et du PARALLÉLISEUR](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
### <a name="to-set-the-qpar-report-compiler-option-in-visual-studio"></a>Pour définir l'option de compilateur /Qpar-report dans Visual Studio  
  
1.  Dans l' **Explorateur de solutions**, ouvrez le menu contextuel du projet et choisissez **Propriétés**.  
  
2.  Dans le **Pages de propriétés** boîte de dialogue **C/C++**, sélectionnez **ligne de commande**.  
  
3.  Dans le **des Options supplémentaires** , entrez `/Qpar-report:1` ou `/Qpar-report:2`.  
  
### <a name="to-set-the-qpar-report-compiler-option-programmatically"></a>Pour définir l'option de compilateur /Qpar-report par programmation  
  
-   Utilisez l'exemple de code fourni dans <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [/Q (opérations de bas niveau), options](../../build/reference/q-options-low-level-operations.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des Options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Programmation parallèle en Code natif](http://go.microsoft.com/fwlink/?LinkId=263662)