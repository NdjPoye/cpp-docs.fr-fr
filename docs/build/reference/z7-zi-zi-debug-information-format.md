---
title: "-Z7, - Zi, - ZI (Format des informations de débogage) | Documents Microsoft"
ms.custom: 
ms.date: 02/22/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.DebugInformationFormat
- /ZI
- /Zi
- /Z7
- VC.Project.VCCLWCECompilerTool.DebugInformationFormat
dev_langs:
- C++
helpviewer_keywords:
- C7 compatible compiler option [C++]
- Debug Information Format compiler option
- ZI compiler option
- -Zi compiler option [C++]
- /ZI compiler option [C++]
- Z7 compiler option [C++]
- debugging [C++], debug information files
- Zi compiler option [C++]
- /Zi compiler option [C++]
- program database compiler option [C++]
- full symbolic debugging information
- /Z7 compiler option [C++]
- line numbers only compiler option [C++]
- cl.exe compiler, debugging options
- -Z7 compiler option [C++]
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f6e3de89c5336cda98960b67b80932df8f67d183
ms.sourcegitcommit: 2cca90d965f76ebf1d741ab901693a15d5b8a4df
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/24/2018
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7, /Zi, /ZI (Format des informations de débogage)

Spécifie le type d’informations de débogage créées pour votre programme et si ces informations sont conservées dans des fichiers objets ou dans un fichier du programme (PDB) de la base de données.

## <a name="syntax"></a>Syntaxe

> **/Z**{**7**|**i**|**I**}  

## <a name="remarks"></a>Notes

Les options de format des informations de débogage sont décrits dans les sections suivantes.  
  
### <a name="none"></a>Aucun.

Par défaut, si aucune option de format d’informations de débogage est spécifiée, le compilateur ne produit aucune information de débogage, d'où une compilation plus rapide.  
  
### <a name="z7"></a>/Z7

Le **/Z7** option génère une *fichier objet*, un fichier qui a une extension .obj, contenant des informations de débogage symboliques complètes pour une utilisation avec le débogueur. Les informations de débogage symboliques comprennent les noms et types des variables, ainsi que les fonctions et les numéros de ligne. Ne *fichier PDB*, un fichier avec l’extension .pdb, est créé.

Pour les distributeurs de bibliothèques tierces, il est avantageux d’un fichier PDB n’ayant ne pas. Toutefois, les fichiers d’objet pour les en-têtes précompilés sont nécessaires pendant la phase de liaison et pour le débogage. S’il existe uniquement type informations (et aucun code) dans les fichiers .pch, vous devez également utiliser le [/Yl (injecter une référence PCH pour une bibliothèque de débogage)](../../build/reference/yl-inject-pch-reference-for-debug-library.md) option, qui est activée par défaut.

### <a name="zi"></a>/ZI

Le **/Zi** option génère un fichier PDB qui contient des informations de type et des informations de débogage symboliques à utiliser avec le débogueur. Les informations de débogage symboliques comprennent les noms et types des variables, ainsi que les fonctions et les numéros de ligne.

Utilisation de **/Zi** n’affecte pas les optimisations. Toutefois, **/Zi** implique **/debug**; consultez [/DEBUG (générer les informations de débogage)](../../build/reference/debug-generate-debug-info.md) pour plus d’informations.

Lorsque **/Zi** est spécifié, les informations de type sont placées dans le fichier PDB et non dans le fichier objet.

Vous pouvez utiliser [/Gm (activer la régénération minimale)](../../build/reference/gm-enable-minimal-rebuild.md) avec **/Zi**, mais **/Gm** n’est pas disponible lorsque **/Z7** est spécifié.

Lorsque vous spécifiez les deux **/Zi** et **/CLR**, le <xref:System.Diagnostics.DebuggableAttribute> attribut n’est pas placé dans les métadonnées de l’assembly. Si vous le souhaitez, vous devez le spécifier dans le code source. Cet attribut peut affecter les performances d'exécution de l'application. Pour plus d’informations sur la façon dont **attribut Debuggable** attribut affecte les performances et la manière dont vous pouvez modifier l’impact des performances, consultez [simplification d’une Image à déboguer](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug).

### <a name="zi"></a>/ZI

Le **/Zi** option génère un fichier PDB dans un format qui prend en charge la [Modifier & Continuer](/visualstudio/debugger/edit-and-continue-visual-cpp) fonctionnalité. Pour utiliser le débogage Modifier & Continuer, cette option est obligatoire. La fonctionnalité Modifier & Continuer est utile pour la productivité des développeurs, mais peut entraîner des problèmes de mise en conformité du compilateur, la taille du code et de performances. Étant donné que la plupart des optimisations sont incompatibles avec Modifier & Continuer, à l’aide **/Zi** désactive toutes `#pragma optimize` instructions dans votre code. Le **/Zi** option est également incompatible avec l’utilisation de la [&#95; &#95; LIGNE &#95; &#95; macro prédéfinie](../../preprocessor/predefined-macros.md). Le code compilé avec **/Zi** ne pouvez pas utiliser **&#95; &#95; LIGNE &#95; &#95;**  comme argument de modèle sans type, bien que **&#95; &#95; LIGNE &#95; &#95;**  peuvent être utilisés dans les expansions de macros.

Le **/Zi** option force à la fois le [/Gy (activer la liaison au niveau des fonctions)](../../build/reference/gy-enable-function-level-linking.md) et [/FC (complet chemin d’accès du fichier de Code Source dans les Diagnostics)](../../build/reference/fc-full-path-of-source-code-file-in-diagnostics.md) options à utiliser dans la compilation.

**/ Zi** n’est pas compatible avec [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md).

> [!NOTE]
> Le **/Zi** option est uniquement disponible dans les compilateurs qui ciblent des processeurs x86 et x64 ; cette option du compilateur n’est pas disponible dans les compilateurs ciblant les processeurs ARM.

Le compilateur nomme le fichier PDB *projet*.pdb. Si vous compilez un fichier en dehors d’un projet, le compilateur crée un fichier PDB nommé VC*x*0.pdb, où *x* est le numéro de version principale de la version de Visual Studio en cours d’utilisation. Le compilateur incorpore le nom de la base de données PDB dans chaque fichier .obj créé avec cette option, afin d'indiquer au débogueur l'emplacement des informations sur les symboles et les numéros de ligne. Lorsque vous utilisez cette option, vos fichiers .obj sont plus petites, car les informations de débogage sont stockées dans le fichier .pdb plutôt que dans les fichiers .obj.

Si vous créez une bibliothèque à partir d'objets compilés avec cette option, le fichier .pdb associé doit être disponible lorsque la bibliothèque est liée à un programme. Ainsi, si vous distribuez la bibliothèque, vous devez aussi distribuer la base de données PDB.

Pour créer une bibliothèque qui contient des informations de débogage sans utiliser de fichiers .pdb, vous devez sélectionner Compatible C du compilateur 7.0 (**/Z7**) option. Si vous utilisez les options des en-têtes précompilés, informations de débogage pour l’en-tête précompilé et le reste du code source sont placée dans le fichier PDB. Le **/Yd** option est ignorée lorsque l’option de base de données du programme est spécifiée.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio

1. Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).

1. Ouvrez le **propriétés de Configuration** > **C/C++** > **général** page de propriétés.

1. Modifier la **Format des informations de débogage** propriété. Choisissez **OK** pour enregistrer vos modifications.

### <a name="to-set-this-compiler-option-programmatically"></a>Pour définir cette option du compilateur par programmation

- Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>.

## <a name="see-also"></a>Voir aussi

[Options du compilateur](../../build/reference/compiler-options.md)  
[Définition des options du compilateur](../../build/reference/setting-compiler-options.md)  

