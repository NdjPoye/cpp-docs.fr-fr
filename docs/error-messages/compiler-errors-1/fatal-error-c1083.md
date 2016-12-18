---
title: "Erreur irr&#233;cup&#233;rable C1083 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1083"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1083"
ms.assetid: 97e52df3-e79c-4f85-8f1e-bbd1057d55e7
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1083
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Impossible d'ouvrir le fichier 'TypeFichier' : 'fichier' : message  
  
 Le compilateur génère une erreur C1083 lorsqu'il ne peut pas trouver un fichier. Voici les raisons usuelles pour lesquelles le compilateur génère cette erreur.  
  
 **Le nom de fichier spécifié est incorrect**  
  
 Le nom d'un fichier est peut-être tapé de façon incorrecte. Par exemple :  
  
```cpp  
#include <algorithms.h>  
```  
  
 ne trouve peut-être pas le fichier souhaité. Il existe un fichier d'en-tête de bibliothèque C++ standard nommé algorithms sans l'extension de nom de fichier .h. Il est introuvable à l'aide de cette directive `include`. Pour résoudre ce problème, vérifiez que le nom de fichier approprié a été entré.  
  
 Certains en-têtes de la bibliothèque runtime C sont situés dans un sous-répertoire du répertoire Include standard. Par exemple, pour inclure sys\types.h, vous devez inclure le nom du sous-répertoire sys dans la directive Include :  
  
 `#include <sys\types.h>`  
  
 **Le fichier n’est pas inclus dans le chemin de recherche du compilateur**  
  
 Le compilateur ne parvient pas à trouver le fichier à l'aide des règles de recherche indiquées par une directive `include` ou `import`. Par exemple, un nom de fichier d'en-tête placé entre guillemets  
  
 `#include "myincludefile.h"`  
  
 indique au compilateur de rechercher d'abord le fichier dans le répertoire qui contient le fichier source, puis d'effectuer la recherche dans d'autres emplacements spécifiés par l'environnement de génération. Si les guillemets contiennent un chemin d'accès absolu, le compilateur recherche uniquement le fichier à cet emplacement. Si les guillemets contiennent un chemin d'accès relatif, le compilateur recherche le fichier dans le répertoire relatif au répertoire source. Si le nom est placé entre crochets  
  
 `#include <stdio.h>`  
  
 le compilateur suit un chemin de recherche défini par l’environnement de génération, le **/I** option du compilateur, la **/X** option du compilateur et le **INCLUDE** variable d’environnement. Pour plus d’informations, y compris des détails spécifiques sur l’ordre de recherche utilisé pour rechercher un fichier, consultez la rubrique [#include, Directive (C/C++)](../../preprocessor/hash-include-directive-c-cpp.md) et [Directive #import](../../preprocessor/hash-import-directive-cpp.md).  
  
 Même lorsque les fichiers d’en-tête sont listés dans **l’Explorateur de solutions** dans le cadre d’un projet, les fichiers sont trouvés uniquement par le compilateur lorsqu’ils sont référencés par un `include` ou `import` la directive et sont situés sur un chemin de recherche de répertoire. Différents genres de builds peuvent utiliser différents chemins d’accès de recherche. Le **/X** option du compilateur peut être utilisée pour exclure les répertoires du chemin de recherche de fichiers include. Cela permet à des builds distinctes d'utiliser des fichiers Include distincts qui portent le même nom, mais qui sont conservés dans des dossiers différents. Il s'agit d'une alternative à la compilation conditionnelle à l'aide de commandes de préprocesseur. Pour plus d’informations sur la **/X** option du compilateur, consultez [/X (ignorer Standard chemins d’accès Include)](../../build/reference/x-ignore-standard-include-paths.md).  
  
 Lorsque le compilateur est appelé sur la ligne de commande, les variables d’environnement sont souvent utilisées pour spécifier des chemins de recherche. Si le chemin de recherche décrit par le **INCLUDE** variable d’environnement n’est pas définie correctement, une erreur C1083 est générée. Pour plus d’informations sur l’utilisation de variables d’environnement, consultez [Comment : utiliser les Variables d’environnement dans une Build](../Topic/How%20to:%20Use%20Environment%20Variables%20in%20a%20Build.md).  
  
 Pour résoudre ce problème, corrigez le chemin d’accès utilisé par le compilateur pour rechercher le fichier inclus ou importé. Un nouveau projet utilise les chemins d'accès de recherche par défaut. Vous devrez peut-être modifier le chemin d’accès pour pouvoir ajouter un dossier à votre projet. Si vous compilez sur la ligne de commande, définissez la **INCLUDE** variable d’environnement ou le **/I** option du compilateur pour spécifier le chemin d’accès du fichier. Pour définir le chemin du répertoire include dans Visual Studio, ouvrez le projet **Pages de propriétés** boîte de dialogue, développez **Propriétés de Configuration** et **répertoires VC ++**, puis modifiez le **répertoires Include** valeur. Pour plus d’informations sur les répertoires par utilisateur et par projet recherché par le compilateur dans Visual Studio, consultez la page [Page de propriétés répertoires VC ++](../../ide/vcpp-directories-property-page.md). Pour plus d’informations sur la **/I** option du compilateur, consultez [/I (autres répertoires Include)](../../build/reference/i-additional-include-directories.md).  
  
 **La version incorrecte d’un nom de fichier est incluse**  
  
 Une erreur C1083 peut également indiquer que la version incorrecte d'un fichier a été incluse. Par exemple, une build peut inclure la mauvaise version d'un fichier qui possède une directive `include` pour un fichier d'en-tête non destiné à cette build. Lorsque le fichier d'en-tête est introuvable, le compilateur génère une erreur C1083. Pour résoudre ce problème, utilisez le fichier approprié. N'ajoutez pas le fichier d'en-tête ou le répertoire à la build.  
  
 **Les en-têtes précompilés ne sont pas encore précompilés**  
  
 Lorsqu’un projet est configuré pour utiliser des en-têtes précompilés, les fichiers .pch appropriés doivent être créés de manière à ce que les fichiers qui utilisent le contenu d’en-tête puissent être compilés. Par exemple, le fichier stdafx.cpp est automatiquement créé dans le répertoire du projet pour les nouveaux projets MFC. Compilez d'abord ce fichier pour créer les fichiers d'en-tête précompilés. (Dans le processus de génération classique, cela se fait automatiquement.) Pour plus d’informations, consultez [Création de fichiers d’en-tête précompilés](../../build/reference/creating-precompiled-header-files.md).  
  
 **Causes supplémentaires**  
  
-   Le fichier utilise du code managé, mais l’option de compilateur **/clr** n’est pas spécifié. Pour plus d’informations, consultez [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
-   Le fichier est compilé à l’aide d’un autre **/ analyze** paramètre de l’option du compilateur que celui utilisé pour la précompilation des en-têtes. (Lorsque les en-têtes d’un projet sont précompilés, tous doivent utiliser le même **/ analyze** paramètres.) Pour plus d’informations, consultez [/analyze (analyse du Code)](../../build/reference/analyze-code-analysis.md).  
  
-   Le fichier, le répertoire ou le disque est en lecture seule.  
  
-   Les autorisations d'accès au fichier ou au répertoire ne sont pas accordées.  
  
-   Il n'y a pas assez de handles de fichiers. Fermez certaines applications, puis recompilez. Cette situation est inhabituelle dans des circonstances normales. Toutefois, elle peut se produire lorsque des projets de grande taille sont générés sur un ordinateur dont la mémoire physique est limitée.  
  
 L'exemple suivant génère une erreur C1083.  
  
```  
// C1083.cpp  
// compile with: /c  
#include "test.h"   // C1083 test.h does not exist  
#include "stdio.h"   // OK  
```  
  
 Pour plus d’informations sur la génération de projets C/C++ dans l’IDE ou sur la ligne de commande et les informations sur la définition des variables d’environnement, consultez [génération de programmes C/C++](../../build/building-c-cpp-programs.md).
 
 ## <a name="see-also"></a>Voir aussi
 [Propriétés MSBuild](MSBuild%20Properties.md)