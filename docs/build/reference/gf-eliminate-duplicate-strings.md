---
title: -GF (supprimer les doublons) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.StringPooling
- VC.Project.VCCLWCECompilerTool.StringPooling
- /gf
dev_langs: C++
helpviewer_keywords:
- duplicate strings
- Eliminate Duplicate Strings compiler option [C++]
- pooling strings compiler option [C++]
- -GF compiler option [C++]
- /GF compiler option [C++]
- GF compiler option [C++]
- strings [C++], pooling
ms.assetid: bb7b5d1c-8e1f-453b-9298-8fcebf37d16c
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0aea115254157ae01292511f25e05a10b6366dff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="gf-eliminate-duplicate-strings"></a>/GF (Supprimer les doublons)
Permet au compilateur de créer une copie unique de chaînes identiques dans l’image de programme et en mémoire pendant l’exécution. Il s’agit d’une optimisation appelée *le regroupement des chaînes* qui peut créer des programmes plus petits.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/GF  
```  
  
## <a name="remarks"></a>Remarques  
 Si vous utilisez **/GF**, le système d’exploitation n’échange pas la partie de la chaîne de la mémoire et peut relire les chaînes à partir du fichier image.  
  
 **/GF** regroupe les chaînes en lecture seule. Si vous essayez de modifier les chaînes sous **/GF**, une erreur d’application se produit.  
  
 Le regroupement des chaînes permet ce qui était censé plusieurs pointeurs vers les tampons de plusieurs pointeurs multiples à une seule mémoire tampon. Dans le code suivant, `s` et `t` sont initialisées avec la même chaîne. Le regroupement des chaînes provoque elles pointent vers la même mémoire :  
  
```  
char *s = "This is a character buffer";  
char *t = "This is a character buffer";  
```  
  
> [!NOTE]
>  Le [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) option, utilisée pour modifier & Continuer, définit automatiquement le **/GF** option.  
  
> [!NOTE]
>  Le **/GF** option du compilateur crée une section adressables pour chaque chaîne unique. Et, par défaut, un fichier objet peut contenir jusqu'à 65 536 sections adressables. Si votre programme contient plus de 65 536 chaînes, utilisez la [/bigobj](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md) créer plus de sections de l’option du compilateur.  
  
 **/GF** est appliqué lorsque [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) ou **/O2** est utilisé.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **C/C++** .  
  
3.  Cliquez sur le **génération de Code** page de propriétés.  
  
4.  Modifier la **activer le regroupement des chaînes** propriété.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)