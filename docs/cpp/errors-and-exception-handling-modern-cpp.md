---
title: "Gestion des erreurs et des exceptions (Modern C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a6c111d0-24f9-4bbb-997d-3db4569761b7
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestion des erreurs et des exceptions (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En C++ moderne, dans la plupart des scénarios, la meilleure façon de signaler et gérer les erreurs de logique et les erreurs d’exécution est d’utiliser des exceptions. Cela est particulièrement vrai lors de la pile peut contenir plusieurs appels de fonction entre la fonction qui détecte l’erreur et la fonction qui présente le contexte de savoir comment la gérer. Exceptions fournissent une manière formelle, bien définie pour le code qui détecte les erreurs pour passer les informations de la pile des appels.  
  
 Erreurs du programme sont généralement répartis en deux catégories : les erreurs de logique provoqués par programmation des erreurs, par exemple, une erreur « index hors limites » et des erreurs d’exécution qui sont en dehors du contrôle du programmeur, par exemple, une erreur « service non disponible de réseau ». Rapport d’erreurs est géré dans la programmation de style C et COM, qui retourne une valeur qui représente un code d’erreur ou un code d’état pour une fonction particulière, ou en définissant une variable globale que l’appelant peut éventuellement récupérer après chaque appel de fonction pour voir si des erreurs ont été signalées. Par exemple, programmation COM utilise la valeur de retour HRESULT pour communiquer des erreurs à l’appelant et l’API Win32 a la fonction GetLastError pour récupérer la dernière erreur a été signalée par la pile des appels. Dans ces deux cas, il incombe à l’appelant de reconnaître le code et d’y répondre en conséquence. Si l’appelant ne gère pas explicitement le code d’erreur, le programme peut se bloquer sans avertissement, ou continuer à s’exécuter avec des données incorrectes et produire des résultats incorrects.  
  
 Les exceptions sont préférables en C++ moderne pour les raisons suivantes :  
  
-   Une exception force le code appelant pour reconnaître une condition d’erreur et la gérer. Exceptions non gérées arrêter l’exécution du programme.  
  
-   Une exception atteint le point dans la pile des appels qui peut gérer l’erreur. Fonctions intermédiaires peuvent laisser l’exception se propager vers. Qu’ils aient à coordonner avec les autres couches.  
  
-   Le mécanisme le déroulement de pile d’exception détruit tous les objets dans la portée en fonction de règles bien définies après qu’une exception est levée.  
  
-   Une exception permet une séparation nette entre le code qui détecte l’erreur et le code qui gère l’erreur.  
  
 L’exemple simplifié suivant illustre la syntaxe nécessaire pour lever et intercepter des exceptions dans C++.  
  
```cpp  
  
#include <stdexcept>  
#include <limits>  
#include <iostream>  
  
using namespace std;  
class MyClass  
{  
public:  
   void MyFunc(char c)  
   {  
      if(c < numeric_limits<char>::max())  
         throw invalid_argument("MyFunc argument too large.");  
      //...  
   }  
};  
  
int main()  
{  
   try  
   {  
      MyFunc(256); //cause an exception to throw  
   }  
  
   catch(invalid_argument& e)  
   {  
      cerr << e.what() << endl;  
      return -1;  
   }  
   //...  
   return 0;  
}  
  
```  
  
 Exceptions dans C++ ressemblent à ceux des langages tels que c# et Java. Dans la `try` bloquer, si une exception est *levée* sera *interceptée* par le premier associés `catch` bloc dont le type correspond à celui de l’exception. En d’autres termes, l’exécution passe à partir de la `throw` instruction à la `catch` instruction. Si aucun bloc catch utilisable est trouvé, `std::terminate` est appelée et le programme se termine. En C++, n’importe quel type peut être levé ; Toutefois, nous vous recommandons de lever un type qui dérive directement ou indirectement de `std::exception`. Dans l’exemple précédent, le type d’exception, [invalid_argument](../standard-library/invalid-argument-class.md), est défini dans la bibliothèque standard dans le [\< stdexcept>](../standard-library/stdexcept.md) fichier d’en-tête. C++ ne fournit pas et n’exige pas, une `finally` bloc pour vous assurer que toutes les ressources sont libérées si une exception est levée. L’acquisition de ressources est l’idiome RAII (initialization), qui utilise des pointeurs intelligents, fournit les fonctionnalités requises pour le nettoyage des ressources. Pour plus d’informations, consultez [Comment : conception pour la sécurité des exceptions](../cpp/how-to-design-for-exception-safety.md). Pour plus d’informations sur le mécanisme de déroulement de pile C++, consultez [Exceptions et déroulement de pile](../cpp/exceptions-and-stack-unwinding-in-cpp.md).  
  
## <a name="basic-guidelines"></a>Instructions de base  
 Gestion des erreurs fiable est difficile dans n’importe quel langage de programmation. Bien que les exceptions fournissent plusieurs fonctionnalités qui prennent en charge une bonne gestion d’erreur, ils ne peuvent pas effectuer tout le travail pour vous. Pour tirer parti du mécanisme d’exception, empêchent les exceptions à l’esprit lorsque vous concevez votre code.  
  
-   Utiliser des assertions pour vérifier les erreurs qui ne doivent jamais se produire. Utiliser des exceptions pour rechercher les erreurs qui peuvent se produire, par exemple, les erreurs de validation des entrées sur les paramètres des fonctions publiques. Pour plus d’informations, consultez la section intitulée **vs d’Exceptions. Assertions**.  
  
-   Utiliser des exceptions lorsque du code qui gère l’erreur peut être séparé du code qui détecte l’erreur par un ou plusieurs appels de fonction intermédiaire. Pensez à utiliser à la place des codes d’erreur dans des boucles critiques pour les performances lorsque le code qui gère l’erreur est fortement couplé au code qui détecte. Pour plus d’informations sur quand ne pas utiliser d’exceptions, consultez [(NOTINBUILD) quand ne pas utiliser les Exceptions](http://msdn.microsoft.com/fr-fr/e810df8b-2217-4e81-bae5-02f0a69f1346).  
  
-   Pour chaque fonction qui peut lever ou propager une exception, fournir parmi les trois garanties d’exception : la garantie forte, la garantie de base ou la garantie nothrow (noexcept). Pour plus d’informations, consultez [Comment : conception pour la sécurité des exceptions](../cpp/how-to-design-for-exception-safety.md).  
  
-   Lever des exceptions par valeur, les intercepter par référence. N’interceptez ne peut pas gérer. Pour plus d’informations, consultez [(NOTINBUILD) les instructions pour la génération et l’interception d’Exceptions (C++)](http://msdn.microsoft.com/fr-fr/0a9b0a3a-64c5-43f5-a080-fca69b89e839).  
  
-   N’utilisez pas les spécifications d’exceptions, qui sont déconseillées dans C ++ 11. Pour plus d’informations, consultez la section intitulée **spécifications d’Exception et noexcept**.  
  
-   Utilisez les types d’exception de bibliothèque standard lorsqu’elles s’appliquent. Dériver des types d’exceptions personnalisées à partir de la [exception, classe](../standard-library/exception-class1.md) hiérarchie. Pour plus d’informations, consultez [(NOTINBUILD) Comment : utiliser les objets d’Exception de bibliothèque Standard](http://msdn.microsoft.com/fr-fr/ad1fb785-ed4e-4d94-8e84-964353aed7b6).  
  
-   Ne pas autoriser les exceptions à soustraire de destructeurs ou de fonctions de désallocation de mémoire.  
  
## <a name="exceptions-and-performance"></a>Exceptions et performances  
 Le mécanisme d’exception a des performances très peu de coût si aucune exception n’est levée. Si une exception est levée, le coût du parcours de pile et déroulement sont à peu près comparable au coût d’un appel de fonction. Structures de données supplémentaires sont requises pour effectuer le suivi de la pile des appels après un `try` bloc est écrit et des instructions supplémentaires sont nécessaires au déroulement de la pile si une exception est levée. Toutefois, dans la plupart des scénarios, le coût des performances et l’encombrement mémoire n’est pas significatif. L’effet négatif des exceptions sur les performances est susceptible d’être significatifs uniquement sur les systèmes très limité en mémoire, ou de performances critiques boucle où une erreur est susceptible de se produire régulièrement et le code de gestion qu’il est étroitement lié au code qui signale. Dans tous les cas, il est impossible de connaître le coût réel des exceptions sans profilage et de mesure. Même dans les rares cas lorsque le coût est important, vous pouvez peser il contre l’exactitude accrue, la facilité de maintenance plus facile et autres avantages offerts par une stratégie d’exception bien conçue.  
  
## <a name="exceptions-vs-assertions"></a>Exceptions et les assertions  
 Exceptions et les assertions sont deux mécanismes distincts pour la détection des erreurs d’exécution dans un programme. Utiliser des assertions pour tester des conditions au cours du développement qui ne doit jamais être true si l’ensemble de votre code est correct. Il n’existe aucun point de gestion de cette erreur à l’aide d’une exception, car l’erreur indique que quelque chose dans le code doit être résolu et ne représente pas une condition que le programme doit récupérer au moment de l’exécution. Une assertion arrête l’exécution à l’instruction de sorte que vous pouvez vérifier l’état du programme dans le débogueur ; une exception poursuit l’exécution à partir du premier gestionnaire catch approprié. Utiliser des exceptions pour vérifier les conditions d’erreur qui peuvent se produire au moment de l’exécution même si votre code est correct, par exemple, « fichier introuvable » ou « mémoire insuffisante. » Vous pouvez souhaiter de remédier à ces conditions, même si la récupération simplement génère un message dans un journal et termine le programme. Vérifiez toujours les arguments des fonctions publiques à l’aide des exceptions. Même si votre fonction est exempt d’erreurs, vous risquez de manquer contrôle complet sur les arguments qu’un utilisateur peut passer à celui-ci.  
  
## <a name="c-exceptions-versus-windows-seh-exceptions"></a>Exceptions C++ et des exceptions SEH de Windows  
 Les programmes C et C++ peuvent utiliser la mécanisme (SEH) dans le système d’exploitation de gestion structurée des exceptions. Les concepts de gestion structurée des Exceptions ressemblent à celles des exceptions C++, sauf que la gestion structurée des Exceptions utilise le `__try`, `__except`, et `__finally` construit au lieu de `try` et `catch`. Dans Visual C++, les exceptions C++ sont implémentées pour la gestion structurée des Exceptions. Toutefois, lorsque vous écrivez du code C++, utilisez la syntaxe d’exception C++.  
  
 Pour plus d’informations sur la gestion structurée des Exceptions, consultez [gestion structurée des exceptions (C/C++)](../cpp/structured-exception-handling-c-cpp.md).  
  
## <a name="exception-specifications-and-noexcept"></a>Noexcept et les spécifications d’exceptions  
 Les spécifications d’exceptions ont été introduites dans C++ comme un moyen de spécifier une fonction peut lever les exceptions. Toutefois, les spécifications d’exceptions prouvée problématiques dans la pratique et sont déconseillées dans la norme C ++ 11 brouillon. Nous vous recommandons de ne pas utiliser les spécifications d’exceptions à l’exception de `throw()`, ce qui indique que l’exception n’autorise aucune exception d’échapper. Si vous devez utiliser des spécifications d’exception du type `throw(`*type*`)`, n’oubliez pas que [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] s’éloigne de la norme de certaines façons. Pour plus d’informations, consultez la page [les spécifications d’exceptions (throw)](../cpp/exception-specifications-throw-cpp.md). Le `noexcept` spécificateur est introduit dans C ++ 11 comme alternative pour `throw()`.  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : Interface entre le Code exceptionnel et Non exceptionnel](../cpp/how-to-interface-between-exceptional-and-non-exceptional-code.md)   
 [Bienvenue dans C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Référence du langage C++](../cpp/cpp-language-reference.md)   
 [Bibliothèque C++ Standard](../standard-library/cpp-standard-library-reference.md)