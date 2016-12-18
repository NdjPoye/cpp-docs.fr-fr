---
title: "Erreur des outils &#201;diteur de liens LNK2019 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_check_commonlanguageruntime_version"
  - "LNK2019"
  - "nochkclr.obj"
ms.assetid: 4392be92-195c-4eb2-bd4d-49cfac3ca291
caps.latest.revision: 39
caps.handback.revision: 37
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK2019
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

symbole externe non résolu « symbol » référencé dans la fonction « function »  
  
 L'éditeur de liens n'a pas pu trouver de définition pour le symbole externe « `symbol` » utilisé dans la fonction « `function` ». Divers problèmes peuvent être à l'origine de cette erreur. Cette rubrique va vous aider à identifier la cause et à trouver une solution.  
  
 Un *symbole externe* est le nom déclaré que vous utilisez dans le code source pour faire référence à un élément défini dans un autre objet ou fichier de bibliothèque, par exemple, une fonction externe ou une variable globale. L’éditeur de liens est chargé de résoudre toutes les références de symboles externes dans chaque fichier objet quand elles sont liées dans une application ou une DLL. Si l'éditeur de liens ne parvient pas à trouver de définition correspondante pour un symbole externe dans aucun des fichiers liés, il génère l'erreur LNK2019. Cette erreur peut se produire si le code source ou le fichier bibliothèque contenant la définition du symbole n'est pas inclus dans la build. Elle peut aussi survenir si le nom recherché par l’éditeur de liens ne correspond pas au nom du symbole dans le module qui le définit.  
  
 Le code qui utilise une liaison C\+\+ a recours à la [Décoration de nom](../../error-messages/tool-errors/name-decoration.md), aussi appelée *substantypage des noms*, pour encoder les informations supplémentaires sur le type et la convention d’appel d’un symbole, en même temps que le nom de ce dernier. Le *nom décoré* est le nom que l'éditeur de liens recherche pour résoudre les symboles externes. Sachant qu'il devient partie intégrante du nom décoré du symbole, si le type de déclaration de la référence du symbole ne correspond pas au type de déclaration de la définition du symbole, l'erreur LNK2019 peut être générée. Le message d'erreur vous indique à la fois le symbole externe et son nom décoré pour vous aider à identifier la cause de l'erreur.  
  
 **Problèmes courants**  
  
 Voici un aperçu des problèmes courants qui provoquent l'erreur LNK2019 :  
  
-   **La déclaration du symbole et sa définition ne sont pas orthographiées de la même façon.** Vérifiez l'orthographe.  
  
-   **Une fonction est utilisée, mais le type ou le nombre de paramètres ne correspondent pas à la définition de la fonction.** La déclaration de la fonction doit correspondre à la définition. Le code qui appelle des fonctions avec modèle doit aussi comporter des déclarations de fonctions avec modèle correspondantes qui incluent les mêmes paramètres de modèle que la définition. Vérifiez que l'appel de fonction correspond à la déclaration et que la déclaration correspond à la définition.  
  
-   **Une fonction ou une variable est déclarée mais pas définie.** Cela signifie généralement qu'une déclaration existe dans un fichier d'en\-tête, mais qu'aucune définition n'est implémentée. Pour les fonctions membres ou les membres de données statiques, l'implémentation doit inclure le sélecteur de portée de classe. Pour obtenir un exemple, consultez [Corps de fonction ou variable manquant](../../error-messages/tool-errors/missing-function-body-or-variable.md).  
  
-   **La convention d'appel est différente entre la déclaration de la fonction et la définition de la fonction.** Les conventions d'appel \([\_\_cdecl](../../cpp/cdecl.md), [\_\_stdcall](../../cpp/stdcall.md), [\_\_fastcall](../../cpp/fastcall.md) ou [\_\_vectorcall](../../cpp/vectorcall.md)\) sont encodées dans le nom décoré. Vérifiez que la convention d'appel est identique.  
  
-   **Un symbole est défini dans un fichier C, mais déclaré sans utiliser extern "C" dans un fichier C\+\+.** Les symboles définis dans un fichier compilé en C ont des noms décorés différents de ceux des symboles déclarés dans un fichier C\+\+, sauf si vous utilisez un modificateur [extern "C"](../../cpp/using-extern-to-specify-linkage.md). Vérifiez que la déclaration correspond à la liaison de compilation pour chaque symbole.  
  
     De même, si vous définissez un symbole dans un fichier C\+\+ qui sera utilisé par un programme C, utilisez `extern "C"` dans la définition.  
  
-   **Un symbole est défini comme étant static et par la suite référencé en dehors du fichier.** En C\+\+, contrairement à C, les [constantes globales](../../error-messages/tool-errors/global-constants-in-cpp.md) ont une liaison `static`. Pour contourner cette limitation, vous pouvez inclure les initialisations `const` dans un fichier d'en\-tête et inclure cet en\-tête dans vos fichiers .cpp. Vous pouvez aussi rendre la variable non constante et utiliser une référence constante pour y accéder.  
  
-   **Un membre statique d'une classe n'est pas défini.** Un membre de classe statique doit avoir une définition unique. À défaut, il enfreint la règle de définition unique. Un membre de classe statique qui ne peut pas être défini comme étant inline doit être défini dans un fichier source à partir de son nom complet. S'il n'est pas du tout défini, l'éditeur de liens génère l'erreur LNK2019.  
  
-   **Une dépendance de génération est définie uniquement comme une dépendance de projet dans la solution.** Dans les versions antérieures de [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)], ce niveau de dépendance était suffisant. Cependant, depuis Visual Studio 2010, [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] nécessite une [référence entre projets](../Topic/Managing%20references%20in%20a%20project.md). Si votre projet n'a pas de référence entre projets, il se peut que vous obteniez cette erreur de l'éditeur de liens. Ajoutez une référence entre projets pour corriger ce problème.  
  
-   **Vous générez une application console en utilisant les paramètres d'une application Windows**. Si le message d’erreur est similaire à **unresolved external symbol WinMain referenced in function** `function_name`, utilisez **\/SUBSYSTEM:CONSOLE** à la place de **\/SUBSYSTEM:WINDOWS** pour établir une liaison. Pour plus d’informations sur ce paramètre et pour obtenir des instructions sur la façon de définir cette propriété dans Visual Studio, consultez [\/SUBSYSTEM \(Spécifier le sous\-système\)](../../build/reference/subsystem-specify-subsystem.md).  
  
-   **Vous utilisez différentes options de compilateur pour incorporer des fonctions inline dans différents fichiers sources.** L’utilisation de fonctions inline définies dans des fichiers .cpp et le panachage d’options de compilateur pour incorporer des fonctions inline dans différents fichiers sources peut occasionner l’erreur LNK2019. Pour plus d'informations, consultez [Problèmes de fonctions inline](../../error-messages/tool-errors/function-inlining-problems.md).  
  
-   **Vous utilisez des variables automatiques en dehors de leur portée.** Les variables automatiques \(portée de fonction\) ne peuvent être utilisées que dans la portée de la fonction en question. Ces variables ne peuvent pas être déclarées comme étant `extern` et utilisées dans d’autres fichiers sources. Pour obtenir un exemple, consultez [Variables automatiques \(portée de fonction\)](../../error-messages/tool-errors/automatic-function-scope-variables.md).  
  
-   **Vous appelez des fonctions intrinsèques ou passez des types d'arguments à des fonctions intrinsèques qui ne sont pas prises en charge dans votre architecture cible.** Par exemple, si vous utilisez une fonction intrinsèque AVX2, mais que vous ne spécifiez pas l'option de compilateur [\/ARCH:AVX2](../../build/reference/arch-x86.md), le compilateur considère que la fonction intrinsèque est une fonction externe. Au lieu de générer une instruction inline, le compilateur génère un appel à un symbole externe avec le même nom que la fonction intrinsèque. Quand l'éditeur de liens tente de trouver la définition de cette fonction manquante, il génère l'erreur LNK2019. Vérifiez que vous utilisez uniquement des fonctions intrinsèques et des types pris en charge par votre architecture cible.  
  
-   **Vous mélangez du code qui utilise le type wchar\_t natif avec du code qui ne l'utilise pas.** Le travail de mise en conformité du langage C\+\+ réalisé dans Visual C\+\+ 2005 a fait de `wchar_t` un type natif par défaut. Vous devez utiliser l’option de compilateur [\/Zc:wchar\_t\-](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) pour générer du code compatible avec les fichiers objets et de bibliothèque compilés à l’aide des versions antérieures de Visual C\+\+. Si tous les fichiers n’ont pas été compilés avec les mêmes paramètres **\/Zc:wchar\_t**, les références de type risquent de ne pas être résolues en types compatibles. Vérifiez la compatibilité des types `wchar_t` dans tous les fichiers objets et de bibliothèque, soit en mettant à jour les types utilisés, soit en utilisant les mêmes paramètres **\/Zc:wchar\_t** au moment de la compilation.  
  
 Pour plus d’informations sur les causes et les solutions possibles de l’erreur LNK2019, accédez au site Stack Overflow et consultez les réponses à la question suivante : [Qu’est\-ce qu’une erreur de référence non définie\/de symbole externe non résolu et comment la corriger ?](http://stackoverflow.com/q/12573816/2002113).  
  
 **Outils de diagnostic**  
  
 Il peut être difficile de déterminer la raison qui empêche l'éditeur de liens de trouver une définition de symbole particulière. Souvent, le problème est lié au fait que le code n'a pas été inclus dans la build ou que les options de génération ont créé des noms décorés différents pour des symboles externes. Il existe plusieurs outils et options qui peuvent vous aider à diagnostiquer une erreur LNK2019.  
  
-   L'option d'éditeur de liens [\/verbose](../../build/reference/verbose-print-progress-messages.md) peut vous aider à identifier les fichiers auxquels l'éditeur de liens fait référence. Cela peut vous aider à vérifier si le fichier qui contient la définition du symbole est inclus dans votre build.  
  
-   Les options [\/EXPORTS](../../build/reference/dash-exports.md) et [\/SYMBOLS](../../build/reference/symbols.md) de l'utilitaire DUMPBIN peuvent vous aider à identifier les symboles qui sont définis dans vos fichiers .dll et objets ou bibliothèques. Vérifiez que les noms décorés exportés correspondent aux noms décorés que l'éditeur de liens recherche.  
  
-   L'utilitaire UNDNAME peut vous indiquer l'équivalent d'un symbole externe non décoré pour un nom décoré.  
  
 **Exemples**  
  
 Voici plusieurs exemples de code qui génèrent une erreur LNK2019, ainsi que des informations permettant de corriger l'erreur.  
  
 **Un symbole est déclaré mais pas défini**  
  
 L'exemple suivant génère l'erreur LNK2019, car un symbole externe est déclaré mais pas défini :  
  
```cpp  
// LNK2019.cpp // Compile by using: cl /EHsc LNK2019.cpp // LNK2019 expected extern char B[100];   // B is not available to the linker int main() { B[0] = ' ';   // LNK2019 }  
```  
  
 Voici un autre exemple :  
  
```cpp  
// LNK2019c.cpp // Compile by using: cl /EHsc LNK2019c.cpp // LNK2019 expected extern int i; extern void g(); void f() { i++; g(); } int main() {}  
```  
  
 Si `i` et `g` ne sont pas définis dans un des fichiers de la build, l'éditeur de liens génère l'erreur LNK2019. Vous pouvez corriger les erreurs en incluant le fichier de code source qui contient les définitions dans le cadre de la compilation. L'autre solution consiste à passer à l'éditeur de liens les fichiers .obj ou .lib qui contiennent les définitions.  
  
 **Un membre de données statique est déclaré mais pas défini**  
  
 L'erreur LNK2019 peut aussi se produire quand un membre de données statique est déclaré mais pas défini. L'exemple suivant génère l'erreur LNK2019 et montre comment la corriger.  
  
```cpp  
// LNK2019b.cpp // Compile by using: cl /EHsc LNK2019b.cpp // LNK2019 expected struct C { static int s; }; // Uncomment the following line to fix the error. // int C::s; int main() { C c; C::s = 1; }  
```  
  
 **Les paramètres de déclaration ne correspondent pas à la définition**  
  
 Le code qui appelle des fonctions avec modèle doit comporter les déclarations de fonction avec modèle correspondantes. Les déclarations doivent inclure les mêmes paramètres de modèle que la définition. L'exemple suivant génère l'erreur LNK2019 sur un opérateur défini par l'utilisateur et montre comment la corriger.  
  
```cpp  
// LNK2019e.cpp // compile by using: cl /EHsc LNK2019e.cpp // LNK2019 expected #include <iostream> using namespace std; template<class T> class Test { // The operator<< declaration does not match the definition below: friend ostream& operator<<(ostream&, Test&); // To fix, replace the line above with the following: // template<typename T> friend ostream& operator<<(ostream&, Test<T>&); }; template<typename T> ostream& operator<<(ostream& os, Test<T>& tt) { return os; } int main() { Test<int> t; cout << "Test: " << t << endl;   // LNK2019 unresolved external }  
```  
  
 **Définitions de type wchar\_t incohérentes**  
  
 L'exemple suivant crée une DLL dans laquelle une exportation utilise `WCHAR`, qui est résolu en `wchar_t`.  
  
```cpp  
// LNK2019g.cpp // compile with: cl /EHsc /LD LNK2019g.cpp #include "windows.h" // WCHAR resolves to wchar_t __declspec(dllexport) void func(WCHAR*) {}  
```  
  
 L'exemple suivant utilise la DLL de l'exemple précédent et génère l'erreur LNK2019, car les types non signés short \* et WCHAR \* ne sont pas identiques.  
  
```cpp  
// LNK2019h.cpp // compile by using: cl /EHsc LNK2019h LNK2019g.lib // LNK2019 expected __declspec(dllimport) void func(unsigned short*); int main() { func(0); }  
```  
  
 Pour résoudre cette erreur, remplacez `unsigned short` par `wchar_t` ou `WCHAR`, ou compilez LNK2019g.cpp en utilisant **\/Zc:wchar\_t\-**.