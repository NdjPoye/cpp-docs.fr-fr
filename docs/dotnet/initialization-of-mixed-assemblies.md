---
title: "Initialisation d’assemblys mixtes | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- mixed assemblies [C++], loader lock
- loader lock [C++]
- initializing mixed assemblies
- deadlocks [C++]
- .cctor [C++]
- custom locales [C++]
- mixed assemblies [C++], initilizing
ms.assetid: bfab7d9e-f323-4404-bcb8-712b15f831eb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e7d192387131ff0eaa04fc366254d7f78a73dd52
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/03/2018
---
# <a name="initialization-of-mixed-assemblies"></a>Initialisation d'assemblys mixtes
Avant Visual Studio 2005, les DLL compilées avec la **/CLR** option du compilateur pourrait non déterministe lors du chargement ; ce problème a été appelé le mixte DLL lors du chargement ou chargeur de problème de verrouillage. Le non-déterminisme a été pratiquement supprimé du processus de chargement de DLL mixtes. Toutefois, il reste quelques scénarios dans lesquels le verrouillage du chargeur peut se produire (de façon déterministe).
  
 Le code situé dans [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583) ne doit pas accéder au CLR. Cela signifie que `DllMain` ne doit pas appeler de fonctions managées, directement ou indirectement ; qu’aucun code managé ne doit être déclaré ou implémenté dans `DllMain`; et qu’aucun garbage collection ou chargement de bibliothèque automatique ne doit avoir lieu dans `DllMain`.  
  
> [!NOTE]
>  Visual C++ 2003 fournit _vcclrit.h pour faciliter l’initialisation des DLL tout en réduisant les risques d’interblocage. L’utilisation de _vcclrit.h n’est plus nécessaire et génère des avertissements de désapprobation pendant la compilation. La stratégie recommandée consiste à supprimer les dépendances sur ce fichier à l’aide des étapes décrites dans [Removing Deprecated Header File _vcclrit.h](http://msdn.microsoft.com/en-us/7881993e-431d-43e9-8c6d-0d2285a4882d). Vous pouvez aussi supprimer les avertissements en définissant `_CRT_VCCLRIT_NO_DEPRECATE` avant d’inclure _vcclrit.h ou ignorer simplement les avertissements de désapprobation, mais ces solutions sont loin d’être idéales.  
  
## <a name="causes-of-loader-lock"></a>Causes du verrouillage du chargeur  
 Avec l’introduction de la plateforme .NET, il existe deux mécanismes distincts pour charger un module d’exécution (EXE ou DLL) : un pour Windows qui est utilisé pour les modules non managés et un pour le Common Language Runtime (CLR) .NET qui charge les assemblys .NET. Le problème du chargement de DLL mixtes se concentre autour du chargeur du système d’exploitation Microsoft Windows.  
  
 Quand un assembly qui contient uniquement des constructions .NET est chargé dans un processus, le chargeur du CLR peut exécuter toutes les tâches de chargement et d’initialisation nécessaires lui-même. Toutefois, dans la mesure où les assemblys mixtes peuvent contenir du code natif et des données, le chargeur Windows doit aussi être utilisé.  
  
 Le chargeur Windows garantit qu’aucun code ne peut accéder au code ou aux données qui se trouvent dans cette DLL avant qu’elle n’ait été initialisée, et qu’aucun code ne peut charger de façon redondante la DLL pendant qu’elle est partiellement initialisée. Pour cela, le chargeur Windows utilise une section critique de processus global (souvent appelée « verrouillage du chargeur ») qui empêche l’accès non sécurisé pendant l’initialisation du module. Le processus de chargement est donc vulnérable pour de nombreux scénarios d’interblocage classiques. Pour les assemblys mixtes, les deux scénarios suivants augmentent le risque d’interblocage :  
  
-   Premièrement, si les utilisateurs tentent d’exécuter des fonctions compilées en langage MSIL (Microsoft Intermediate Language) quand le verrouillage du chargeur est maintenu (à partir de `DllMain` ou dans les initialiseurs statiques, par exemple), un interblocage peut se produire. Prenons le cas d’une fonction MSIL faisant référence à un type dans un assembly qui n’a pas été chargé. Le CLR tente de charger automatiquement cet assembly, ce qui peut nécessiter le blocage du chargeur Windows sur le verrouillage du chargeur. Dans la mesure où le verrouillage du chargeur est déjà maintenu par du code contenu précédemment dans la séquence d’appel, un interblocage en résulte. Toutefois, l’exécution du langage MSIL pendant le verrouillage du chargeur ne garantit pas un interblocage, ce qui rend ce scénario difficile à diagnostiquer et à résoudre. Dans certaines circonstances, par exemple quand la DLL du type référencé ne contient pas de constructions natives et qu’aucune de ses dépendances ne contient de constructions natives, le chargeur Windows n’est pas contraint de charger l’assembly .NET du type référencé. En outre, l’assembly exigé ou ses dépendances natives/.NET mixtes ont peut-être déjà été chargés par un autre code. L’interblocage peut donc être difficile à prédire et peut varier selon la configuration de l’ordinateur cible.  
  
-   Deuxièmement, pendant le chargement de DLL dans les versions 1.0 et 1.1 du .NET Framework, le CLR supposait que le verrouillage du chargeur n’était pas maintenu et exécutait plusieurs actions qui n’étaient pas valides pendant le verrouillage du chargeur. Supposer que le verrouillage du chargeur n’est pas maintenu est une hypothèse valide pour les DLL exclusivement .NET, mais, comme les DLL mixtes exécutent des routines d’initialisation natives, elles nécessitent le chargeur Windows natif et donc le verrouillage du chargeur. Ainsi, même si le développeur n’essayait pas d’exécuter des fonctions MSIL pendant l’initialisation des DLL, il persistait un faible risque d’interblocage non déterministe avec les versions 1.0 et 1.1 du .NET Framework.  
  
 Le non-déterminisme a été entièrement supprimé du processus de chargement de DLL mixtes grâce aux modifications suivantes :  
  
-   Le CLR ne fait plus de fausses hypothèses lors du chargement de DLL mixtes.  
  
-   L’initialisation non managée et managée est exécutée en deux étapes distinctes. L’initialisation non managée a lieu en premier (par le biais de DllMain), suivie de l’initialisation managée, par l’intermédiaire d’une construction prise en charge par .NET et appelée *.cctor*. Cette dernière opération est complètement transparente pour l’utilisateur, sauf si **/Zl** ou **/NODEFAULTLIB** est utilisé. Pour plus d’informations, consultez[/NODEFAULTLIB (Ignore Libraries)](../build/reference/nodefaultlib-ignore-libraries.md) et [/Zl (Omit Default Library Name)](../build/reference/zl-omit-default-library-name.md) .  
  
 Le verrouillage du chargeur peut encore se produire, mais il est désormais détecté et se produit de façon déterministe. Si DllMain contient des instructions MSIL, le compilateur génère l’avertissement [Compiler Warning (level 1) C4747](../error-messages/compiler-warnings/compiler-warning-level-1-c4747.md). En outre, le CRT ou le CLR tente de détecter et de signaler les tentatives d’exécution du MSIL pendant le verrouillage du chargeur. La détection du CRT se traduit par le diagnostic du runtime C Run-Time Error R6033.  
  
 Le reste de ce document décrit les autres scénarios dans lesquels des instructions MSIL peuvent s’exécuter pendant le verrouillage du chargeur, les solutions au problème dans chacun de ces scénarios et les techniques de débogage.  
  
## <a name="scenarios-and-workarounds"></a>Scénarios et solutions de contournement  
 Dans plusieurs cas de figure, le code utilisateur peut exécuter des instructions MSIL pendant le verrouillage du chargeur. Le développeur doit s’assurer que l’implémentation du code utilisateur ne tente pas d’exécuter des instructions MSIL dans chacune de ces circonstances. Les sous-sections suivantes décrivent toutes les possibilités tout en indiquant comment résoudre les problèmes dans les cas les plus courants.  
  
-   `DllMain`  
  
-   Initialiseurs statiques  
  
-   Fonctions fournies par l’utilisateur affectant le démarrage  
  
-   Paramètres régionaux personnalisés  
  
### <a name="dllmain"></a>DllMain  
 La fonction `DllMain` est un point d’entrée défini par l’utilisateur pour une DLL. Sauf indication contraire de l’utilisateur, la fonction `DllMain` est appelée chaque fois qu’un processus ou un thread s’attache à la DLL conteneur ou s’en détache. Dans la mesure où cet appel peut se produire alors que le verrouillage du chargeur est maintenu, aucune fonction `DllMain` fournie par l’utilisateur ne doit être compilée en langage MSIL. En outre, aucune fonction dans l’arborescence des appels associée à une racine `DllMain` ne peut être compilée en langage MSIL. Pour résoudre les problèmes à cet emplacement, le bloc de code qui définit `DllMain` doit être modifié avec #pragma `unmanaged`. Il en va de même pour chaque fonction que `DllMain` appelle.  
  
 Dans les cas où ces fonctions doivent appeler une fonction qui nécessite une implémentation MSIL pour d’autres contextes appelants, une stratégie de duplication peut être utilisée quand une version .NET et une version native de la même fonction sont créées.  
  
 Sinon, si `DllMain` n’est pas nécessaire ou qu’il est inutile de l’exécuter pendant le verrouillage du chargeur, l’implémentation de `DllMain` fournie par l’utilisateur peut être supprimée, ce qui élimine le problème.  
  
 Si DllMain tente d’exécuter des instructions MSIL directement, vous obtenez l’avertissement suivant : [Compiler Warning (level 1) C4747](../error-messages/compiler-warnings/compiler-warning-level-1-c4747.md) . Toutefois, le compilateur ne peut pas détecter les cas où DllMain appelle une fonction dans un autre module qui, à son tour, tente d’exécuter des instructions MSIL.  
  
 Pour plus d’informations sur ce scénario, consultez « Obstacles au diagnostic ».  
  
### <a name="initializing-static-objects"></a>Initialisation d'objets statiques  
 L’initialisation d’objets statiques peut entraîner un interblocage si un initialiseur dynamique est exigé. Pour les cas simples, par exemple quand une variable statique est simplement assignée à une valeur connue au moment de la compilation, aucune initialisation dynamique n’est exigée ; il n’y a donc aucun risque d’interblocage. Toutefois, les variables statiques initialisées par les appels de fonction, les appels de constructeur ou les expressions qui ne peuvent pas être évaluées au moment de la compilation exigent tous une exécution de code pendant l’initialisation de module.  
  
 Le code suivant montre des exemples d’initialiseurs statiques qui exigent une initialisation dynamique : un appel de fonction, une construction d’objet et une initialisation de pointeur. (Ces exemples ne sont pas statiques, mais sont supposés être définis dans la portée globale, ce qui a le même effet.)  
  
```  
// dynamic initializer function generated  
int a = init();  
CObject o(arg1, arg2);    
CObject* op = new CObject(arg1, arg2);  
```  
  
 Ce risque d’interblocage varie selon que le module conteneur est compilé avec **/clr** et que les instructions MSIL sont exécutées. Plus particulièrement, si la variable statique est compilée sans **/clr** (ou réside dans un bloc #pragma `unmanaged` ) et que l’initialiseur dynamique nécessaire pour l’initialiser entraîne l’exécution d’instructions MSIL, un interblocage peut se produire. Ceci est dû au fait que l’initialisation de variables statiques est exécutée par DllMain pour les modules compilés sans **/clr**. En revanche, les variables statiques compilées avec **/clr** sont initialisées par le .cctor, une fois l’étape d’initialisation non managée terminée et le verrouillage du chargeur désactivé.  
  
 Il existe de nombreuses méthodes permettant de résoudre l’interblocage provoqué par l’initialisation dynamique de variables statiques (classées globalement selon le délai nécessaire pour résoudre le problème) :  
  
-   Le fichier source contenant la variable statique peut être compilé avec **/clr**.  
  
-   Toutes les fonctions appelées par la variable statique peuvent être compilées en code natif à l’aide de la directive #pragma `unmanaged` .  
  
-   Clonez manuellement le code dont dépend la variable statique, en fournissant à la fois une version .NET et une version native avec des noms différents. Les développeurs peuvent ensuite appeler la version native à partir d’initialiseurs statiques natifs et appeler la version .NET ailleurs.  
  
### <a name="user-supplied-functions-affecting-startup"></a>Fonctions fournies par l’utilisateur affectant le démarrage  
 Il existe plusieurs fonctions fournies par l’utilisateur dont dépendent les bibliothèques pour l’initialisation au démarrage. Par exemple, lors de la surcharge globale d’opérateurs en C++ telles que la `new` et `delete` opérateurs, les versions fournies par l’utilisateur sont utilisées partout, y compris dans l’initialisation de la bibliothèque Standard C++ et la destruction. Bibliothèque C++ Standard et les initialiseurs statiques fournis par l’utilisateur appelle en conséquence, les versions fournies par l’utilisateur de ces opérateurs.  
  
 Si les versions fournies par l’utilisateur sont compilées en langage MSIL, ces initialiseurs tentent alors d’exécuter des instructions MSIL pendant que le verrouillage du chargeur est maintenu. Un malloc fourni par l’utilisateur a les mêmes conséquences. Pour résoudre ce problème, n’importe laquelle de ces surcharges ou définitions fournies par l’utilisateur doit être implémentée sous la forme de code natif à l’aide de la directive #pragma `unmanaged` .  
  
 Pour plus d’informations sur ce scénario, consultez « Obstacles au diagnostic ».  
  
### <a name="custom-locales"></a>Paramètres régionaux personnalisés  
 Si l’utilisateur fournit des paramètres régionaux globaux personnalisés, ceux-ci sont utilisés pour initialiser tous les futurs flux d’E/S, notamment ceux qui sont initialisés de façon statique. Si cet objet de paramètres régionaux globaux est compilé en langage MSIL, les fonctions membres d’objets de paramètres régionaux compilées en langage MSIL peuvent être appelées pendant que le verrouillage du chargeur est maintenu.  
  
 Il existe trois options pour résoudre ce problème :  
  
 Les fichiers sources contenant toutes les définitions de flux d’E/S globales peuvent être compilés à l’aide de l’option **/clr** , ce qui empêche l’exécution de leurs initialiseurs statiques pendant le verrouillage du chargeur.  
  
 Les définitions de fonctions personnalisées de paramètres régionaux peuvent être compilées en code natif en utilisant la directive #pragma `unmanaged` .  
  
 Abstenez-vous de définir les paramètres régionaux personnalisés comme paramètres régionaux globaux tant que le verrouillage du chargeur n’a pas été désactivé. Configurez ensuite de façon explicite les flux d’E/S créés pendant l’initialisation avec les paramètres régionaux personnalisés.  
  
## <a name="impediments-to-diagnosis"></a>Obstacles au diagnostic  
 Dans certains cas, il est difficile de détecter la source des interblocages. Les sous-sections suivantes présentent ces scénarios et la façon de contourner ces problèmes.  
  
### <a name="implementation-in-headers"></a>Implémentation dans les en-têtes  
 Dans des cas spécifiques, les implémentations de fonctions à l’intérieur des fichiers d’en-tête peuvent compliquer le diagnostic. Les fonctions inline et le code du modèle exigent que les fonctions soient spécifiées dans un fichier d’en-tête.  Le langage C++ spécifie la règle de définition unique, qui force toutes les implémentations de fonctions ayant le même nom à être sémantiquement équivalentes. L’éditeur de liens C++ n’a pas besoin de faire de considérations spéciales quand il fusionne des fichiers objets qui ont des implémentations en double d’une fonction donnée.  
  
 Avant Visual Studio 2005, l’éditeur de liens choisit simplement la plus importante de ces définitions sémantiquement équivalentes, pour prendre en charge des scénarios et des déclarations anticipées lorsque différentes options d’optimisation sont utilisées pour les fichiers sources différents. Cela crée un problème pour les DLL natives/.NET mixtes.  
  
 Dans la mesure où le même en-tête peut à la fois être inclus par un fichier CPP avec le commutateur **/clr** activé et désactivé, ou qu’une instruction #include peut être incluse dans un wrapper à l’intérieur d’un bloc #pragma `unmanaged` , il est possible d’avoir à la fois les versions MSIL et natives des fonctions qui fournissent les implémentations dans les en-têtes. Les implémentations MSIL et natives ont des sémantiques différentes en ce qui concerne l’initialisation pendant le verrouillage du chargeur, ce qui viole en pratique la règle de définition unique. Quand l’éditeur de liens choisit l’implémentation la plus importante, il peut donc choisir la version MSIL d’une fonction, même si elle a été compilée explicitement ailleurs en code natif à l’aide de la directive #pragma unmanaged. Pour faire en sorte qu’une version MSIL d’un modèle ou d’une fonction inline ne soit jamais appelée pendant le verrouillage du chargeur, chaque définition de chaque fonction de ce genre appelée pendant le verrouillage du chargeur doit être modifiée à l’aide de la directive #pragma `unmanaged` . Si le fichier d’en-tête provient d’un tiers, le moyen le plus simple pour y parvenir consiste à exécuter les méthodes Push et Pop sur la directive #pragma unmanaged autour de la directive #include pour le fichier d’en-tête incriminé (Consultez [managé, non managé](../preprocessor/managed-unmanaged.md) pour obtenir un exemple.) Toutefois, cette stratégie ne fonctionne pas pour les en-têtes qui contiennent un autre code qui doit appeler directement des API .NET.  
  
 À titre de commodité pour les utilisateurs confrontés au verrouillage du chargeur, l’éditeur de liens choisit l’implémentation native par rapport à l’implémentation managée en cas de présentation des deux implémentations.  Cela évite les problèmes précités.  Toutefois, il y a deux exceptions à cette règle dans cette version en raison de deux problèmes non résolus avec le compilateur :  
  
-   L’appel de la fonction inline s’effectue à travers un pointeur de fonction statique globale.  Ce scénario est particulièrement intéressant, parce que les fonctions virtuelles sont appelées à travers des pointeurs de fonction globale.  Par exemple :  
  
```  
#include "definesmyObject.h"  
#include "definesclassC.h"  
  
typedef void (*function_pointer_t)();  
  
function_pointer_t myObject_p = &myObject;  
  
#pragma unmanaged  
void DuringLoaderlock(C & c)  
{  
    // Either of these calls could resolve to a managed implementation,   
    // at link-time, even if a native implementation also exists.  
    c.VirtualMember();  
    myObject_p();  
}  
```  
  
-   Avec la compilation ciblée Itanium, il existe un bogue dans l’implémentation de tous les pointeurs de fonction.  Dans l’exemple précédent, si myObject_p était défini localement à l’intérieur de during_loaderlock(), l’appel peut également être résolu en une implémentation managée.  
  
### <a name="diagnosing-in-debug-mode"></a>Diagnostic en mode débogage  
 Toutes les opérations de diagnostic des problèmes liés au verrouillage du chargeur doivent être effectuées sur des builds Debug. Les builds Release ne peuvent pas produire de diagnostic et les optimisations réalisées en mode Release peuvent masquer une partie du langage MSIL dans les scénarios de verrouillage du chargeur.  
  
## <a name="how-to-debug-loader-lock-issues"></a>Comment déboguer les problèmes de verrouillage du chargeur  
 Le diagnostic que le CLR génère quand une fonction MSIL est appelée provoque l’interruption de l’exécution du CLR. Cela entraîne ensuite l’interruption du débogueur en mode mixte de Visual C++ durant l’exécution du programme débogué in-process. Toutefois, lors de l’attachement au processus, il n’est pas possible d’obtenir une pile des appels managée pour le programme débogué à l’aide du débogueur mixte.  
  
 Pour identifier la fonction MSIL spécifique qui a été appelée pendant le verrouillage du chargeur, les développeurs doivent effectuer les étapes suivantes :  
  
1.  Vérifiez que les symboles de mscoree.dll et mscorwks.dll sont disponibles.  
  
     Cette opération peut être effectuée de deux façons. Premièrement, les fichiers PDB de mscoree.dll et mscorwks.dll peuvent être ajoutés au chemin de recherche de symboles. Pour ce faire, ouvrez la boîte de dialogue des options du chemin de recherche de symboles. (Dans le menu Outils, cliquez sur Options. Dans le volet gauche de la boîte de dialogue Options, ouvrez le nœud Débogage et cliquez sur Symboles.) Ajoutez le chemin aux fichiers PDB de mscoree.dll et mscorwks.dll à la liste de recherche. Ces PDB sont installés dans %VSINSTALLDIR%\SDK\v2.0\symbols. Cliquez sur OK.  
  
     Deuxièmement, les fichiers PDB de mscoree.dll et mscorwks.dll peuvent être téléchargés à partir du serveur de symboles Microsoft. Pour configurer le serveur de symboles, ouvrez la boîte de dialogue des options du chemin de recherche de symboles. (Dans le menu Outils, cliquez sur Options. Dans le volet gauche de la boîte de dialogue Options, ouvrez le nœud Débogage et cliquez sur Symboles.) Ajoutez le chemin de recherche http://msdl.microsoft.com/download/symbols à la liste de recherche. Ajoutez un répertoire de cache de symboles à la zone de texte du cache du serveur de symboles. Cliquez sur OK.  
  
2.  Définissez le mode du débogueur en mode natif uniquement.  
  
     Pour ce faire, ouvrez la grille Propriétés du projet de démarrage dans la solution. Sous la sous-arborescence Propriétés de configuration, sélectionnez le nœud Débogage. Affectez au champ Type de débogueur la valeur Natif uniquement.  
  
3.  Démarrez le débogueur (F5).  
  
4.  Quand le diagnostic **/clr** est généré, cliquez sur Réessayer, puis sur Arrêter.  
  
5.  Ouvrez la fenêtre Pile des appels. (Dans le menu Déboguer, cliquez sur Windows, puis sur Pile des appels.) Si incriminé `DllMain` ou initialiseur statique est identifié avec une flèche verte. Si la fonction incriminée n’est pas identifiée, vous devez effectuer les étapes suivantes pour la rechercher.  
  
6.  Ouvrez la fenêtre Exécution (dans le menu Déboguer, cliquez sur Fenêtres, puis sur Exécution).  
  
7.  Tapez .load sos.dll dans la fenêtre Exécution pour charger le service de débogage SOS.  
  
8.  Tapez !dumpstack dans la fenêtre Exécution pour obtenir une liste complète de la pile **/clr** interne.  
  
9. Recherchez la première instance (la plus proche du bas de la pile) de _CorDllMain (si `DllMain` est à l’origine du problème), ou de _VTableBootstrapThunkInitHelperStub ou GetTargetForVTableEntry (si l’initialiseur statique est à l’origine du problème).  L’entrée de la pile juste en dessous de cet appel est l’appel de la fonction MSIL implémentée qui a tenté de s’exécuter pendant le verrouillage du chargeur.  
  
10. Accédez au fichier source et au numéro de ligne identifiés à l’étape 9, puis corrigez le problème à l’aide des scénarios et des solutions décrits dans la section Scénarios.  
  
## <a name="example"></a>Exemple  
  
### <a name="description"></a>Description  
 L’exemple suivant montre comment éviter le verrouillage du chargeur en déplaçant le code de DllMain vers le constructeur d’un objet global.  
  
 Cet exemple comprend un objet managé global dont le constructeur contient l’objet managé initialement présent dans DllMain. La deuxième partie de cet exemple référence l’assembly, en créant une instance de l’objet managé pour appeler le constructeur de module qui exécute l’initialisation.  
  
### <a name="code"></a>Code  
  
```  
// initializing_mixed_assemblies.cpp  
// compile with: /clr /LD   
#pragma once  
#include <stdio.h>  
#include <windows.h>  
struct __declspec(dllexport) A {  
   A() {  
      System::Console::WriteLine("Module ctor initializing based on global instance of class.\n");  
   }  
  
   void Test() {  
      printf_s("Test called so linker does not throw away unused object.\n");  
   }  
};  
  
#pragma unmanaged  
// Global instance of object  
A obj;  
  
extern "C"  
BOOL WINAPI DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved) {  
   // Remove all managed code from here and put it in constructor of A.  
   return true;  
}  
```  
  
## <a name="example"></a>Exemple  
  
### <a name="code"></a>Code  
  
```  
// initializing_mixed_assemblies_2.cpp  
// compile with: /clr initializing_mixed_assemblies.lib  
#include <windows.h>  
using namespace System;  
#include <stdio.h>  
#using "initializing_mixed_assemblies.dll"  
struct __declspec(dllimport) A {  
   void Test();  
};  
  
int main() {  
   A obj;  
   obj.Test();  
}  
```  
  
### <a name="output"></a>Sortie  
  
```  
Module ctor initializing based on global instance of class.  
  
Test called so linker does not throw away unused object.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Assemblys mixtes (natif et managé)](../dotnet/mixed-native-and-managed-assemblies.md)