---
title: "L’erreur LNK2019 erreur des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 05/17/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2019
dev_langs:
- C++
helpviewer_keywords:
- nochkclr.obj
- LNK2019
- _check_commonlanguageruntime_version
ms.assetid: 4392be92-195c-4eb2-bd4d-49cfac3ca291
caps.latest.revision: 39
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4cb4413b8c0b53b407724dd16083027b89b91b37
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="linker-tools-error-lnk2019"></a>Erreur des outils Éditeur de liens LNK2019
symbole externe non résolu '*symbole*'référencé dans la fonction'*fonction*'  
  
Le code compilé pour *fonction* rend une référence ou un appel à *symbole*, mais ce symbole n’est pas défini dans une des bibliothèques ou des fichiers d’objet spécifiés à l’éditeur de liens.  
  
Ce message d’erreur est suivi d’une erreur irrécupérable [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md). Vous devez corriger les erreurs de tous les LNK2001 et l’erreur LNK2019 pour résoudre l’erreur LNK1120.  
  
## <a name="possible-causes"></a>Causes possibles  
  
Il existe plusieurs façons d’obtenir cette erreur, mais tous les impliquent une référence à une fonction ou une variable qui n’est pas l’éditeur de liens *résoudre*, ou de trouver une définition pour. Le compilateur peut identifier quand un symbole n’est pas *déclaré*, mais pas lorsqu’il n’est pas *défini*, car la définition peut être dans un autre fichier source ou la bibliothèque. Si un symbole est référencé mais jamais défini, l’éditeur de liens génère une erreur de symbole externe non résolu.  
  
Voici un aperçu des problèmes courants qui provoquent l'erreur LNK2019 :  
  
-   **Le fichier objet ou la bibliothèque qui contient la définition du symbole n’est pas lié.** Dans Visual Studio, vérifiez que le fichier source qui contient la définition est construit et lié en tant que partie de votre projet. Sur la ligne de commande, vérifiez que le fichier source qui contient la définition est compilé, et que le fichier objet résultant est inclus dans la liste des fichiers à lier.  
  
-   **La déclaration du symbole et sa définition ne sont pas orthographiées de la même façon.** Vérifiez l’orthographe et la casse est utilisé dans la déclaration et la définition et, là où le symbole est utilisé ou appelé.  
  
-   **Une fonction est utilisée, mais le type ou le nombre de paramètres ne correspondent pas à la définition de la fonction.** La déclaration de la fonction doit correspondre à la définition. Vérifiez que l'appel de fonction correspond à la déclaration et que la déclaration correspond à la définition. Le code qui appelle des fonctions avec modèle doit aussi comporter des déclarations de fonctions avec modèle correspondantes qui incluent les mêmes paramètres de modèle que la définition. Pour obtenir un exemple d’une incompatibilité de déclaration de modèle, consultez l’exemple LNK2019e.cpp dans la section Exemples.  
  
-   **Une fonction ou une variable est déclarée mais pas définie.** Cela signifie généralement une déclaration existe dans un fichier d’en-tête, mais aucune définition correspondante n’est implémentée. Pour les fonctions membres ou les membres de données statiques, l'implémentation doit inclure le sélecteur de portée de classe. Pour obtenir un exemple, consultez [Missing Function Body or Variable](../../error-messages/tool-errors/missing-function-body-or-variable.md).  
  
-   **La convention d'appel est différente entre la déclaration de la fonction et la définition de la fonction.** Les conventions d'appel ([__cdecl](../../cpp/cdecl.md), [__stdcall](../../cpp/stdcall.md), [__fastcall](../../cpp/fastcall.md)ou [__vectorcall](../../cpp/vectorcall.md)) sont encodées dans le nom décoré. Vérifiez que la convention d'appel est identique.  
  
-   **Un symbole est défini dans un fichier C, mais déclaré sans utiliser extern "C" dans un fichier C++.** Les symboles définis dans un fichier compilé en C ont des noms décorés différents de ceux des symboles déclarés dans un fichier C++, sauf si vous utilisez un modificateur [extern "C"](../../cpp/using-extern-to-specify-linkage.md) . Vérifiez que la déclaration correspond à la liaison de compilation pour chaque symbole. De même, si vous définissez un symbole dans un fichier C++ qui sera utilisé par un programme C, utilisez `extern "C"` dans la définition.  
  
-   **Un symbole est défini comme étant static et par la suite référencé en dehors du fichier.** En C++, contrairement à C, les [constantes globales](../../error-messages/tool-errors/global-constants-in-cpp.md) ont une liaison `static` . Pour contourner cette limitation, vous pouvez inclure les initialisations `const` dans un fichier d'en-tête et inclure cet en-tête dans vos fichiers .cpp. Vous pouvez aussi rendre la variable non constante et utiliser une référence constante pour y accéder.  
  
-   **Un membre statique d'une classe n'est pas défini.** Un membre de classe statique doit avoir une définition unique. À défaut, il enfreint la règle de définition unique. Un membre de classe statique qui ne peut pas être défini comme étant inline doit être défini dans un fichier source à partir de son nom complet. S'il n'est pas du tout défini, l'éditeur de liens génère l'erreur LNK2019.  
  
-   **Une dépendance de génération est définie uniquement comme une dépendance de projet dans la solution.** Dans les versions antérieures de Visual Studio, ce niveau de dépendance était suffisant. Toutefois, à compter de Visual Studio 2010, Visual Studio requiert un [référence de projet à projet](/visualstudio/ide/managing-references-in-a-project). Si votre projet n'a pas de référence entre projets, il se peut que vous obteniez cette erreur de l'éditeur de liens. Ajoutez une référence entre projets pour corriger ce problème.  
  
-   **Vous générez une application console en utilisant les paramètres d'une application Windows**. Si le message d’erreur est similaire à **unresolved external symbol WinMain referenced in function**`function_name`, utilisez **/SUBSYSTEM:CONSOLE** à la place de **/SUBSYSTEM:WINDOWS**. Pour plus d’informations sur ce paramètre et pour obtenir des instructions sur la façon de définir cette propriété dans Visual Studio, consultez [/SUBSYSTEM (Specify Subsystem)](../../build/reference/subsystem-specify-subsystem.md).  
  
-   **Vous utilisez différentes options de compilateur pour incorporer des fonctions inline dans différents fichiers sources.** L’utilisation de fonctions inline définies dans des fichiers .cpp et le panachage d’options de compilateur pour incorporer des fonctions inline dans différents fichiers sources peut occasionner l’erreur LNK2019. Pour plus d'informations, consultez [Function Inlining Problems](../../error-messages/tool-errors/function-inlining-problems.md).  
  
-   **Vous utilisez des variables automatiques en dehors de leur portée.** Les variables automatiques (portée de fonction) ne peuvent être utilisées que dans la portée de la fonction en question. Ces variables ne peuvent pas être déclarées comme étant `extern` et utilisées dans d’autres fichiers sources. Pour obtenir un exemple, consultez [Automatic (Function Scope) Variables](../../error-messages/tool-errors/automatic-function-scope-variables.md).  
  
-   **Vous appelez des fonctions intrinsèques ou passez des types d'arguments à des fonctions intrinsèques qui ne sont pas prises en charge dans votre architecture cible.** Par exemple, si vous utilisez une fonction intrinsèque AVX2, mais que vous ne spécifiez pas l'option de compilateur [/ARCH:AVX2](../../build/reference/arch-x86.md) , le compilateur considère que la fonction intrinsèque est une fonction externe. Au lieu de générer une instruction inline, le compilateur génère un appel à un symbole externe avec le même nom que la fonction intrinsèque. Quand l'éditeur de liens tente de trouver la définition de cette fonction manquante, il génère l'erreur LNK2019. Vérifiez que vous utilisez uniquement des fonctions intrinsèques et des types pris en charge par votre architecture cible.  
  
-   **Vous mélangez du code qui utilise wchar native\_t avec du code qui ne.** Le travail de mise en conformité du langage C++ réalisé dans Visual C++ 2005 a fait de `wchar_t` un type natif par défaut. Vous devez utiliser l’option de compilateur [/Zc:wchar_t-](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) pour générer du code compatible avec les fichiers objets et de bibliothèque compilés à l’aide des versions antérieures de Visual C++. Si tous les fichiers ont été compilés à l’aide de la même **/Zc:wchar\_t** des paramètres, tapez les références ne peuvent pas résolues en types compatibles. Vérifiez la compatibilité des types `wchar_t` dans tous les fichiers objets et de bibliothèque, soit en mettant à jour les types utilisés, soit en utilisant les mêmes paramètres **/Zc:wchar_t** au moment de la compilation.  
  
## <a name="diagnosis-tools"></a>Outils de diagnostic    
  
Il peut être difficile de déterminer la raison qui empêche l'éditeur de liens de trouver une définition de symbole particulière. Fréquence à laquelle le problème est que vous n’avez pas inclus le code qui contient la définition de votre build ou build options ont créées différents des noms de symboles externes décorés. Il existe plusieurs outils et options qui peuvent vous aider à diagnostiquer une erreur LNK2019.  
  
-   L'option d'éditeur de liens [/verbose](../../build/reference/verbose-print-progress-messages.md) peut vous aider à identifier les fichiers auxquels l'éditeur de liens fait référence. Cela peut vous aider à vérifier si le fichier qui contient la définition du symbole est inclus dans votre build.  
  
-   Les options [/EXPORTS](../../build/reference/dash-exports.md) et [/SYMBOLS](../../build/reference/symbols.md) de l'utilitaire DUMPBIN peuvent vous aider à identifier les symboles qui sont définis dans vos fichiers .dll et objets ou bibliothèques. Vérifiez que les noms décorés exportés correspondent aux noms décorés que l'éditeur de liens recherche.  
  
-   L'utilitaire UNDNAME peut vous indiquer l'équivalent d'un symbole externe non décoré pour un nom décoré.  
## <a name="examples"></a>Exemples  
  
Voici plusieurs exemples de code qui génèrent une erreur LNK2019, ainsi que des informations permettant de corriger l'erreur.  
  
### <a name="a-symbol-is-declared-but-not-defined"></a>Un symbole est déclaré mais pas défini  
  
Dans cet exemple, une variable externe est déclarée mais pas définie :  
  
```cpp  
// LNK2019.cpp  
// Compile by using: cl /EHsc /W4 LNK2019.cpp  
// LNK2019 expected  
extern char B[100];   // B is not available to the linker  
int main() {  
   B[0] = ' ';   // LNK2019  
}  
```  
  
Voici un autre exemple où une variable et fonction sont déclarés comme `extern` , mais aucune définition n’est fournie :  
  
```cpp  
// LNK2019c.cpp  
// Compile by using: cl /EHsc LNK2019c.cpp  
// LNK2019 expected  
extern int i;  
extern void g();  
void f() {  
   i++;  
   g();  
}  
int main() {}  
```  
  
À moins que `i` et `g` sont définis dans un des fichiers inclus dans la build, l’éditeur de liens génère l’erreur LNK2019. Vous pouvez corriger les erreurs en incluant le fichier de code source qui contient les définitions dans le cadre de la compilation. Vous pouvez également transmettre les fichiers .obj ou .lib qui contiennent les définitions à l’éditeur de liens.  
  
### <a name="a-static-data-member-is-declared-but-not-defined"></a>Un membre de données statique est déclaré mais pas défini  
  
L'erreur LNK2019 peut aussi se produire quand un membre de données statique est déclaré mais pas défini. L'exemple suivant génère l'erreur LNK2019 et montre comment la corriger.  
  
```cpp  
// LNK2019b.cpp  
// Compile by using: cl /EHsc LNK2019b.cpp  
// LNK2019 expected  
struct C {  
   static int s;  
};  
  
// Uncomment the following line to fix the error.  
// int C::s;  
  
int main() {  
   C c;  
   C::s = 1;  
}  
```  
  
### <a name="declaration-parameters-do-not-match-definition"></a>Les paramètres de déclaration ne correspondent pas à la définition  
  
Le code qui appelle des fonctions avec modèle doit comporter les déclarations de fonction avec modèle correspondantes. Les déclarations doivent inclure les mêmes paramètres de modèle que la définition. L'exemple suivant génère l'erreur LNK2019 sur un opérateur défini par l'utilisateur et montre comment la corriger.  
  
```cpp  
// LNK2019e.cpp  
// compile by using: cl /EHsc LNK2019e.cpp  
// LNK2019 expected  
#include <iostream>  
using namespace std;  
  
template<class T> class   
Test {  
   // The operator<< declaration does not match the definition below:  
   friend ostream& operator<<(ostream&, Test&);  
   // To fix, replace the line above with the following:  
   // template<typename T> friend ostream& operator<<(ostream&, Test<T>&);  
};  
  
template<typename T>  
ostream& operator<<(ostream& os, Test<T>& tt) {  
   return os;  
}  
  
int main() {  
   Test<int> t;  
   cout << "Test: " << t << endl;   // LNK2019 unresolved external  
}  
```  
  
### <a name="inconsistent-wchart-type-definitions"></a>Définitions de type wchar_t incohérentes  
  
Cet exemple crée une DLL qui possède une exportation utilise `WCHAR`, ce qui donne `wchar_t`.  
  
```cpp  
// LNK2019g.cpp  
// compile with: cl /EHsc /LD LNK2019g.cpp  
#include "windows.h"  
// WCHAR resolves to wchar_t  
__declspec(dllexport) void func(WCHAR*) {}  
```  
  
L’exemple suivant utilise la DLL dans l’exemple précédent et génère l’erreur LNK2019, car les types non signés short * et WCHAR\* ne sont pas identiques.  
  
```cpp  
// LNK2019h.cpp  
// compile by using: cl /EHsc LNK2019h LNK2019g.lib  
// LNK2019 expected  
__declspec(dllimport) void func(unsigned short*);  
  
int main() {  
   func(0);  
}  
```  
  
 Pour corriger cette erreur, modifiez `unsigned short` à `wchar_t` ou `WCHAR`, ou compilez LNK2019g.cpp en utilisant **/Zc:wchar_t-**.  
  
## <a name="additional-resources"></a>Ressources supplémentaires  
  
Pour plus d’informations sur les causes et solutions pour LNK2001, consultez la question Stack Overflow [qu’est une erreur de symbole externe non défini référence/non résolu et comment la corriger ?](http://stackoverflow.com/q/12573816/2002113).  


