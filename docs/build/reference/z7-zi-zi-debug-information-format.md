---
title: "-Z7, - Zi, - ZI (Format des informations de débogage) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.DebugInformationFormat
- /zi
- /z7
- VC.Project.VCCLWCECompilerTool.DebugInformationFormat
dev_langs: C++
helpviewer_keywords:
- C7 compatible compiler option [C++]
- -Zl compiler option [C++]
- Debug Information Format compiler option
- ZI compiler option
- -Zi compiler option [C++]
- /ZI compiler option [C++]
- Z7 compiler option [C++]
- debugging [C++], debug information files
- Zi compiler option [C++]
- none compiler option [C++]
- /Zi compiler option [C++]
- program database compiler option [C++]
- full symbolic debugging information
- /Z7 compiler option [C++]
- line numbers only compiler option [C++]
- cl.exe compiler, debugging options
- -Z7 compiler option [C++]
ms.assetid: ce9fa7e1-0c9b-47e3-98ea-26d1a16257c8
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0b80339192a7d335b0989ac8a67446c0f5716a76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7, /Zi, /ZI (Format des informations de débogage)
Sélectionne le type d'informations de débogage créées pour votre programme et spécifie si ces informations doivent être conservées dans des fichiers objets (.obj) ou dans une base de données de programme (PDB).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/Z{7|i|I}  
```  
  
## <a name="remarks"></a>Notes  
 Les options sont décrites dans le tableau suivant.  
  
 Aucun  
 Ne génère pas d'informations de débogage, d'où une compilation plus rapide.  
  
 **/ Z7**  
 Produit un fichier .obj contenant des informations de débogage symboliques complètes pour une utilisation avec le débogueur. Les informations de débogage symboliques comprennent les noms et types des variables, ainsi que les fonctions et les numéros de ligne. Aucun fichier .pdb n'est produit.  
  
 L'absence de fichier .pdb peut présenter un avantage pour les distributeurs de bibliothèques tierces. Toutefois, les fichiers .obj pour les en-têtes précompilés sont nécessaires pendant la phase de chaînage et lors du débogage. S’il existe uniquement type informations (et aucun code) dans les fichiers .pch, vous devez également compiler avec [/Yl (injecter une référence PCH pour une bibliothèque de débogage)](../../build/reference/yl-inject-pch-reference-for-debug-library.md).  
  
 **/ Zi**  
 Produit une base de données de programme (PDB) qui contient des informations de type et des informations de débogage symboliques à utiliser avec le débogueur. Les informations de débogage symboliques comprennent les noms et types des variables, ainsi que les fonctions et les numéros de ligne.  
  
 **/ Zi** n’affecte pas les optimisations. Toutefois, **/Zi** implique **/debug**; consultez [/DEBUG (générer les informations de débogage)](../../build/reference/debug-generate-debug-info.md) pour plus d’informations.  
  
 Les informations de type sont placées dans le fichier .pdb, et non dans le fichier .obj.  
  
 Vous pouvez utiliser [/Gm (activer la régénération minimale)](../../build/reference/gm-enable-minimal-rebuild.md) avec **/Zi**, alors que **/Gm** n’est pas disponible lors de la compilation avec **/Z7**.  
  
 Lors de la compilation avec **/Zi** et **/CLR**, le <xref:System.Diagnostics.DebuggableAttribute> attribut ne sera pas placé dans les métadonnées de l’assembly ; vous devez le spécifier dans le code source, si vous le souhaitez. Cet attribut peut affecter les performances d'exécution de l'application. Pour plus d’informations sur la façon dont l’attribut Debuggable affecte les performances et comment vous pouvez modifier l’impact des performances, consultez [simplification d’une Image à déboguer](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug).  
  
 **/ ZI**  
 Produit une base de données de programme, telle que décrite ci-dessus, dans un format prenant en charge la fonctionnalité Modifier Continuer. Pour utiliser le débogage Modifier & Continuer, cette option est obligatoire. Étant donné que la plupart des optimisations sont incompatibles avec Modifier & Continuer, à l’aide **/Zi** désactive toutes `#pragma optimize` instructions dans votre code.  
  
 **/ Zi** entraîne [/Gy (activer la liaison au niveau des fonctions)](../../build/reference/gy-enable-function-level-linking.md) et [/FC (complet chemin d’accès du fichier de Code Source dans les Diagnostics)](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md) à utiliser dans la compilation.  
  
 **/ Zi** n’est pas compatible avec [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
> [!NOTE]
>  **/ Zi** est disponible uniquement dans les compilateurs qui ciblent des processeurs x86 et x64 ; cette option du compilateur n’est pas disponible dans les compilateurs ciblant les processeurs ARM.  
  
 Le compilateur nomme la base de données de programme *projet*.pdb. Si vous compilez un fichier sans un projet, le compilateur crée une base de données nommée VC*x*0.PDB où *x* est la version principale de [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] en cours d’utilisation. Le compilateur incorpore le nom de la base de données PDB dans chaque fichier .obj créé avec cette option, afin d'indiquer au débogueur l'emplacement des informations sur les symboles et les numéros de ligne. Lorsque vous utilisez cette option, vos fichiers .obj sont plus compacts puisque les informations de débogage ne sont pas stockées dans ces fichiers, mais dans le fichier .pdb.  
  
 Si vous créez une bibliothèque à partir d'objets compilés avec cette option, le fichier .pdb associé doit être disponible lorsque la bibliothèque est liée à un programme. Ainsi, si vous distribuez la bibliothèque, vous devez aussi distribuer la base de données PDB.  
  
 Pour créer une bibliothèque qui contient des informations de débogage sans utiliser de fichiers .pdb, vous devez sélectionner Compatible C du compilateur 7.0 (**/Z7**) option. Si vous utilisez les options des en-têtes précompilés, les informations de débogage de l’en-tête précompilé et du reste du code source sont placées dans la base de données PDB. Le **/Yd** option est ignorée lorsque l’option de base de données du programme est spécifiée.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l’environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **C/C++** .  
  
3.  Cliquez sur le **général** page de propriétés.  
  
4.  Modifier la **Format des informations de débogage** propriété.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)