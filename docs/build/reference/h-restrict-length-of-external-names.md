---
title: -H (limiter la longueur des noms externes) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /h
dev_langs:
- C++
helpviewer_keywords:
- public name length
- /H compiler option [C++]
- H compiler option [C++]
- external names
- -H compiler option [C++]
ms.assetid: de701dd3-ed04-4c88-8195-960d2520ec2e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d5e862eb8e45d1f2558592c0bb54c1adb9305f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="h-restrict-length-of-external-names"></a>/H (Limiter la longueur des noms externes)
Obsolète. Limite la longueur des noms externes.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/Hnumber  
```  
  
## <a name="arguments"></a>Arguments  
 `number`  
 Spécifie la longueur maximale des noms externes autorisés dans un programme.  
  
## <a name="remarks"></a>Notes  
 Par défaut, la longueur des noms externes (publics) est limitée à 2 047 caractères. Cela est vrai pour les programmes C et C++. À l’aide de **/H** peut seulement diminuer la longueur maximale autorisée d’identificateurs, pas l’augmenter. Un espace entre **/H** et `number` est facultatif.  
  
 Si un programme contient des noms externes plus `number`, les caractères supplémentaires sont ignorées. Si vous compilez un programme sans **/H** et si un identificateur contient plus de 2 047 caractères, le compilateur générera [irrécupérable C1064 d’erreur](../../error-messages/compiler-errors-1/fatal-error-c1064.md).  
  
 La longueur limite inclut tout créé par le compilateur trait de soulignement (_) ou signe arobase (@). Ces caractères font partie de l’identificateur et occupent un emplacement particulier.  
  
-   Le compilateur ajoute un trait de soulignement (_) aux noms modifiés par la `__cdecl` (par défaut) et `__stdcall` conventions d’appel et un signe arobase (@) aux noms modifiés par la `__fastcall` convention d’appel.  
  
-   Le compilateur ajoute des informations de taille des arguments aux noms modifiés par la `__fastcall` et `__stdcall` conventions d’appel et ajoute les informations de type aux noms C++.  
  
 Vous souhaiterez peut-être **/H** utiles :  
  
-   Lorsque vous créez des programmes portables ou à plusieurs langues.  
  
-   Lorsque vous utilisez des outils qui imposent des limites sur la longueur des identificateurs externes.  
  
-   Lorsque vous souhaitez limiter la quantité d’espace utilisée par les symboles dans une version debug.  
  
 L’exemple suivant montre comment l’utilisation **/H** réellement peut introduire des erreurs si les longueurs des identificateurs sont trop limitées :  
  
```cpp  
// compiler_option_H.cpp  
// compile with: /H5  
// processor: x86  
// LNK2005 expected  
void func1(void);  
void func2(void);  
  
int main() { func1(); }  
  
void func1(void) {}  
void func2(void) {}  
```  
  
 Vous devez également être prudent lorsque vous utilisez la **/H** option en raison des identificateurs prédéfinis du compilateur. Si la longueur maximale de l’identificateur est trop petite, certains identificateurs prédéfinis sera bibliothèque non résolues, ainsi que certaines les appels de fonction. Par exemple, si le `printf` fonction est utilisée et l’option **/H5** n’est spécifiée au moment de la compilation, le symbole **_prin** sera créé pour référencer `printf`, et il ne sera pas trouvée dans la bibliothèque.  
  
 Utilisation de **/H** n’est pas compatible avec [/GL (optimisation de l’ensemble du programme)](../../build/reference/gl-whole-program-optimization.md).  
  
 Le **/H** option est déconseillée depuis Visual Studio 2005 ; les limites de longueur maximale ont été augmentées et **/H** n’est plus nécessaire. Pour obtenir la liste des options du compilateur déconseillées, consultez **déconseillées et supprimées des Options du compilateur** dans [Options du compilateur classées par catégorie](../../build/reference/compiler-options-listed-by-category.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **C/C++** .  
  
3.  Cliquez sur la page de propriétés **Ligne de commande** .  
  
4.  Tapez l'option de compilateur dans la zone **Options supplémentaires** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)