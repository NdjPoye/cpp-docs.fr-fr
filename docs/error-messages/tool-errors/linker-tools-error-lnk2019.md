---
title: "L’erreur LNK2019 erreur des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 86b43f2688b6e1dbfb39dfec681ca9adafd2c093
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk2019"></a>Erreur des outils Éditeur de liens LNK2019
symbole externe non résolu « symbol » référencé dans la fonction « function »  
  
 L'éditeur de liens n'a pas pu trouver de définition pour le symbole externe «`symbol`» utilisé dans la fonction «`function`».  
  
 Divers problèmes peuvent être à l'origine de cette erreur. Cette rubrique va vous aider à identifier la cause et à trouver une solution.  
  
 A *symbole* est le nom que le compilateur utilise pour une fonction ou une variable globale. Un *symbole externe* est le nom utilisé pour faire référence à un symbole est défini dans un autre fichier source ou objet. L’éditeur de liens doit *résoudre*, ou de trouver la définition de symbole externe pour chaque fonction ou une variable globale utilisée par chaque fichier compilé lorsqu’elle est liée à une application ou une DLL. Si l'éditeur de liens ne parvient pas à trouver de définition correspondante pour un symbole externe dans aucun des fichiers liés, il génère l'erreur LNK2019.  
  
 Cette erreur peut se produire si l’objet ou le fichier bibliothèque contenant la définition d’un symbole n’est pas inclus dans la build. Il peut également se produire si l’éditeur de liens recherche le nom du symbole ne correspond pas le nom du symbole dans le fichier de bibliothèque ou un objet qui le définit. Cela peut se produire si le nom dans le code appelant est mal orthographié, utilise la mise en majuscule, utilise une autre convention d’appel ou spécifie des paramètres différents.  
  
 Le code qui utilise une liaison C++ utilise [décoration de nom](../../error-messages/tool-errors/name-decoration.md), également appelés *-troncage*, pour encoder les informations supplémentaires sur une variable ou de la fonction type convention d’appel et le nom du symbole. Le *nom décoré* est le nom que l'éditeur de liens recherche pour résoudre les symboles externes. Étant donné que les informations de type deviennent une partie du nom décoré du symbole, LNK2019 peut être générée si la déclaration du symbole externe où il est utilisé ne correspond pas à la déclaration du symbole dans laquelle il est défini. Pour vous aider à déterminer la cause de l’erreur, le message d’erreur vous indique les deux le « nom convivial » le nom utilisé dans le code source et le nom décoré (entre parenthèses) pour le symbole externe non résolu. Vous n’avez pas besoin de savoir comment traduire le nom décoré pour être en mesure de comparer avec les autres noms décorés.  
  
 **Problèmes courants**  
  
 Voici un aperçu des problèmes courants qui provoquent l'erreur LNK2019 :  
  
-   **Le fichier objet ou la bibliothèque qui contient la définition du symbole n’est pas lié.** Dans Visual Studio, vérifiez que le fichier source qui contient la définition est créé et lié dans le cadre de votre projet. Sur la ligne de commande, vérifiez que le fichier source qui contient la définition est compilé, et que le fichier objet qui en résulte est inclus dans la liste des fichiers à lier.  
  
-   **La déclaration du symbole n'est pas la même orthographe que la définition du symbole.** Vérifiez l’orthographe et la casse est utilisé dans la déclaration et la définition et, là où le symbole est utilisé ou appelé.  
  
-   **Une fonction est utilisée, mais le type ou le nombre de paramètres ne correspondent pas à la définition de fonction.** La déclaration de la fonction doit correspondre à la définition. Vérifiez que l'appel de fonction correspond à la déclaration et que la déclaration correspond à la définition. Le code qui appelle des fonctions avec modèle doit aussi comporter des déclarations de fonctions avec modèle correspondantes qui incluent les mêmes paramètres de modèle que la définition. Pour obtenir un exemple d’une incompatibilité de déclaration de modèle, consultez l’exemple LNK2019e.cpp dans la section Exemples.  
  
-   **Une fonction ou une variable est déclarée mais pas défini.** Cela signifie généralement une déclaration existe dans un fichier d’en-tête, mais aucune définition correspondante n’est implémentée. Pour les fonctions membres ou les membres de données statiques, l'implémentation doit inclure le sélecteur de portée de classe. Pour obtenir un exemple, consultez [manquant un corps de fonction ou Variable](../../error-messages/tool-errors/missing-function-body-or-variable.md).  
  
-   **La convention d’appel est différente entre la déclaration de fonction et la définition de fonction.** Conventions d’appel ([__cdecl](../../cpp/cdecl.md), [__stdcall](../../cpp/stdcall.md), [__fastcall](../../cpp/fastcall.md), ou [__vectorcall](../../cpp/vectorcall.md)) sont encodées dans le nom décoré. Vérifiez que la convention d'appel est identique.  
  
-   **Un symbole est défini dans un fichier C, mais déclaré sans utiliser extern « C » dans un fichier C++.** Symboles définis dans un fichier qui est compilé en C ont des noms décorés différents de ceux des symboles déclarés dans un fichier C++, sauf si vous utilisez un [extern « C »](../../cpp/using-extern-to-specify-linkage.md) modificateur. Vérifiez que la déclaration correspond à la liaison de compilation pour chaque symbole.  
  
     De même, si vous définissez un symbole dans un fichier C++ qui sera utilisé par un programme C, utilisez `extern "C"` dans la définition.  
  
-   **Un symbole est défini comme étant static et par la suite référencé en dehors du fichier.** En C++, contrairement à C, [constantes globales](../../error-messages/tool-errors/global-constants-in-cpp.md) a `static` une liaison. Pour contourner cette limitation, vous pouvez inclure les initialisations `const` dans un fichier d'en-tête et inclure cet en-tête dans vos fichiers .cpp. Vous pouvez aussi rendre la variable non constante et utiliser une référence constante pour y accéder.  
  
-   **Un membre statique d’une classe n’est pas défini.** Un membre de classe statique doit avoir une définition unique. À défaut, il enfreint la règle de définition unique. Un membre de classe statique qui ne peut pas être défini comme étant inline doit être défini dans un fichier source à partir de son nom complet. S'il n'est pas du tout défini, l'éditeur de liens génère l'erreur LNK2019.  
  
-   **Une dépendance de génération est définie uniquement comme une dépendance de projet dans la solution.** Dans les versions antérieures de [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)], ce niveau de dépendance était suffisant. Cependant, depuis Visual Studio 2010, [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] nécessite un [référence de projet à projet](/visualstudio/ide/managing-references-in-a-project). Si votre projet n'a pas de référence entre projets, il se peut que vous obteniez cette erreur de l'éditeur de liens. Ajoutez une référence entre projets pour corriger ce problème.  
  
-   **Vous générez une application console en utilisant les paramètres d'une application Windows**. Si le message d’erreur est similaire à **unresolved external symbol WinMain referenced in function**`function_name`, utilisez **/SUBSYSTEM:CONSOLE** à la place de **/SUBSYSTEM:WINDOWS**. Pour plus d’informations sur ce paramètre et pour obtenir des instructions sur la façon de définir cette propriété dans Visual Studio, consultez [/SUBSYSTEM (spécifier le sous-système)](../../build/reference/subsystem-specify-subsystem.md).  
  
-   **Vous utilisez différentes options de compilateur pour incorporer des fonctions inline dans différents fichiers source.** L’utilisation de fonctions inline définies dans des fichiers .cpp et le panachage d’options de compilateur pour incorporer des fonctions inline dans différents fichiers sources peut occasionner l’erreur LNK2019. Pour plus d’informations, consultez [problèmes de fonctions inline](../../error-messages/tool-errors/function-inlining-problems.md).  
  
-   **Vous utilisez des variables automatiques hors de portée.** Les variables automatiques (portée de fonction) ne peuvent être utilisées que dans la portée de la fonction en question. Ces variables ne peuvent pas être déclarées comme étant `extern` et utilisées dans d’autres fichiers sources. Pour obtenir un exemple, consultez [les Variables automatiques (portée de fonction)](../../error-messages/tool-errors/automatic-function-scope-variables.md).  
  
-   **Vous appelez des fonctions intrinsèques ou passez des types d’arguments à des fonctions intrinsèques qui ne sont pas pris en charge dans votre architecture cible.** Par exemple, si vous utilisez une fonction intrinsèque AVX2, mais que vous ne spécifiez pas le [/arch : avx2](../../build/reference/arch-x86.md) option du compilateur, le compilateur suppose que l’intrinsèque est une fonction externe. Au lieu de générer une instruction inline, le compilateur génère un appel à un symbole externe avec le même nom que la fonction intrinsèque. Quand l'éditeur de liens tente de trouver la définition de cette fonction manquante, il génère l'erreur LNK2019. Vérifiez que vous utilisez uniquement des fonctions intrinsèques et des types pris en charge par votre architecture cible.  
  
-   **Vous mélangez du code qui utilise le type wchar_t natif avec du code qui ne fait pas.** Le travail de mise en conformité du langage C++ réalisé dans Visual C++ 2005 a fait de `wchar_t` un type natif par défaut. Vous devez utiliser le [/Zc:wchar_t-](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) option du compilateur pour générer le code compatible avec les fichiers de bibliothèque et les objets compilés à l’aide de versions antérieures de Visual C++. Si tous les fichiers n’ont pas été compilés avec les mêmes paramètres **/Zc:wchar_t** , les références de type risquent de ne pas être résolues en types compatibles. Vérifiez la compatibilité des types `wchar_t` dans tous les fichiers objets et de bibliothèque, soit en mettant à jour les types utilisés, soit en utilisant les mêmes paramètres **/Zc:wchar_t** au moment de la compilation.  
  
 Pour plus d’informations sur les causes et les solutions possibles de l’erreur LNK2019, accédez au site Stack Overflow et consultez les réponses à la question suivante : [Qu’est-ce qu’une erreur de référence non définie/de symbole externe non résolu et comment la corriger ?](http://stackoverflow.com/q/12573816/2002113).  
  
 **Outils de diagnostic**  
  
 Il peut être difficile de déterminer la raison qui empêche l'éditeur de liens de trouver une définition de symbole particulière. Souvent, le problème est lié au fait que le code n'a pas été inclus dans la build ou que les options de génération ont créé des noms décorés différents pour des symboles externes. Il existe plusieurs outils et options qui peuvent vous aider à diagnostiquer une erreur LNK2019.  
  
-   Le [/verbose](../../build/reference/verbose-print-progress-messages.md) option de l’éditeur de liens peut vous aider à identifier les fichiers auxquels les références de l’éditeur de liens. Cela peut vous aider à vérifier si le fichier qui contient la définition du symbole est inclus dans votre build.  
  
-   Le [/EXPORTS](../../build/reference/dash-exports.md) et [/symboles](../../build/reference/symbols.md) options de l’utilitaire DUMPBIN peuvent vous aider à identifier les symboles qui sont définis dans vos fichiers .dll et objets ou bibliothèques. Vérifiez que les noms décorés exportés correspondent aux noms décorés que l'éditeur de liens recherche.  
  
-   L'utilitaire UNDNAME peut vous indiquer l'équivalent d'un symbole externe non décoré pour un nom décoré.  
  
 **Exemples**  
  
 Voici plusieurs exemples de code qui génèrent une erreur LNK2019, ainsi que des informations permettant de corriger l'erreur.  
  
 **Un symbole est déclaré mais pas défini**  
  
 L'exemple suivant génère l'erreur LNK2019, car un symbole externe est déclaré mais pas défini :  
  
```cpp  
// LNK2019.cpp  
// Compile by using: cl /EHsc LNK2019.cpp  
// LNK2019 expected  
extern char B[100];   // B is not available to the linker  
int main() {  
   B[0] = ' ';   // LNK2019  
}  
```  
  
 Voici un autre exemple :  
  
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
  
 Si `i` et `g` ne sont pas définis dans un des fichiers de la build, l'éditeur de liens génère l'erreur LNK2019. Vous pouvez corriger les erreurs en incluant le fichier de code source qui contient les définitions dans le cadre de la compilation. L'autre solution consiste à passer à l'éditeur de liens les fichiers .obj ou .lib qui contiennent les définitions.  
  
 **Un membre de données statique est déclaré mais pas défini**  
  
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
  
 **Paramètres de déclaration ne correspondent pas à la définition**  
  
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
  
 **Définitions de type wchar_t incohérentes**  
  
 L'exemple suivant crée une DLL dans laquelle une exportation utilise `WCHAR`, qui est résolu en `wchar_t`.  
  
```cpp  
// LNK2019g.cpp  
// compile with: cl /EHsc /LD LNK2019g.cpp  
#include "windows.h"  
// WCHAR resolves to wchar_t  
__declspec(dllexport) void func(WCHAR*) {}  
```  
  
 L’exemple suivant utilise la DLL de l’exemple précédent et génère l’erreur LNK2019, car les types non signés short * et WCHAR\* ne sont pas identiques.  
  
```cpp  
// LNK2019h.cpp  
// compile by using: cl /EHsc LNK2019h LNK2019g.lib  
// LNK2019 expected  
__declspec(dllimport) void func(unsigned short*);  
  
int main() {  
   func(0);  
}  
```  
  
 Pour résoudre cette erreur, modifiez `unsigned short` à `wchar_t` ou `WCHAR`, ou compilez LNK2019g.cpp en utilisant **/Zc:wchar_t-**.
