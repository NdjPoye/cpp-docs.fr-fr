---
title: "Comment&#160;: exposer un conteneur STL/CLR d&#39;un assembly | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STL/CLR conteneurs (STL/CLR)"
  - "STL/CLR, problèmes inter-assembly"
ms.assetid: 87efb41b-3db3-4498-a2e7-f3ef8a99f04d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Comment&#160;: exposer un conteneur STL/CLR d&#39;un assembly
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les conteneurs STL\/CLR tels que `list` et `map` sont implémentés en tant que modèles de classes de référence.  Étant donné que les modèles C\+\+ sont instanciés au moment de la compilation, deux classes de modèle ayant exactement la même signature mais se trouvant dans des assemblys différents sont en fait des types différents.  Cela signifie que les classes du modèle ne peuvent pas être utilisées en\-dehors des limites de l'assembly.  
  
 Pour rendre le partage d'assembly croisé possible, les conteneurs STL\/CLR implémentent l'interface générique <xref:System.Collections.Generic.ICollection%601>.  À l'aide de cette interface générique, tous les langages qui prennent en charge les génériques, notamment C\+\+, C\# et Visual Basic, peuvent accéder aux conteneurs STL ou CLR.  
  
 Cette rubrique vous montre comment afficher les éléments de plusieurs conteneurs STL\/CLR écrits dans un assembly C\+\+ nommé `StlClrClassLibrary`.  Nous indiquons deux assemblys pour accéder à `StlClrClassLibrary`.  Le premier assembly est écrit en C\+\+, et le second en C\#.  
  
 Si les deux assemblys sont écrits en C\+\+, vous pouvez accéder à l'interface générique d'un conteneur à l'aide de son typedef `generic_container`.  Par exemple, si vous avez un conteneur de type `cliext::vector<int>`, alors son interface générique est : `cliext::vector<int>::generic_container`.  De même, vous pouvez obtenir une itération au sein de l'interface générique à l'aide du typedef `generic_iterator`, comme dans : `cliext::vector<int>::generic_iterator`.  
  
 Comme ces typedefs sont déclarés dans les fichiers d'en\-tête C\+\+, les assemblys écrits dans d'autres langages ne peuvent pas les utiliser.  Par conséquent, pour accéder à l'interface générique pour `cliext::vector<int>` en C\# ou en tout autre langage .NET, utilisez `System.Collections.Generic.ICollection<int>`.  Pour effectuer une itération au sein de la collection, utilisez une boucle `foreach`.  
  
 Le tableau suivant répertorie l'interface générique que chaque conteneur STL\/CLR implémente :  
  
|Conteneur STL\/CLR|Interface générique|  
|------------------------|-------------------------|  
|deque\<T\>|ICollection\<T\>|  
|hash\_map\<K, V\>|IDictionary\<K, V\>|  
|hash\_multimap\<K, V\>|IDictionary\<K, V\>|  
|hash\_multiset\<T\>|ICollection\<T\>|  
|hash\_set\<T\>|ICollection\<T\>|  
|list\<T\>|ICollection\<T\>|  
|map\<K, V\>|IDictionary\<K, V\>|  
|multimap\<K, V\>|IDictionary\<K, V\>|  
|multiset\<T\>|ICollection\<T\>|  
|set\<T\>|ICollection\<T\>|  
|vector\<T\>|ICollection\<T\>|  
  
> [!NOTE]
>  Comme les conteneurs `queue`, `priority_queue`, `stack` ne prennent pas en charge les itérateurs, ils n'implémentent pas les interfaces génériques et ne peuvent pas posséder un accès en assembly croisé.  
  
## Exemple 1  
  
### Description  
 Dans cet exemple, nous déclarons la classe actuelle c \+\+ qui contient des données privées membres de STL\/CLR.  Nous déclarons alors les méthodes publiques pour accorder un accès aux collections privées de la classe.  Nous le faisons de deux façons différentes, l'une pour les clients C\+\+ et l'autre pour les autres clients .NET.  
  
### Code  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## Exemple 2  
  
### Description  
 Dans cet exemple, nous implémentons la classe déclarée dans l'exemple 1.  Pour que les clients utilisent cette bibliothèque de classes, nous utilisons l'outil manifeste **mt.exe** pour inclure le fichier de manifeste dans la DLL.  Pour plus d'informations, consultez les commentaires de code.  
  
 Pour plus d'informations sur l'outil et les assemblys côte à côte manifestes, consultez [Génération d'applications isolées C\/C\+\+ et d'assemblys côte à côte](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md).  
  
### Code  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## Exemple 3  
  
### Description  
 Dans cet exemple, nous créons un client C \+\+ qui utilise la bibliothèque de classes créée dans les exemples 1 et 2.  Ce client utilise les typedefs `generic_container` des conteneurs STL\/CLR pour parcourir les conteneurs et afficher leur contenu.  
  
### Code  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
### Sortie  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
## Exemple 4  
  
### Description  
 Dans cet exemple, nous créons un client C\# qui utilise la bibliothèque de classes créée dans les exemples 1 et 2.  Ce client utilise les méthodes <xref:System.Collections.Generic.ICollection%601> des conteneurs STL\/CLR pour parcourir les conteneurs et afficher leur contenu.  
  
### Code  
  
```  
// CsConsoleApp.cs  
// compile with: /r:Microsoft.VisualC.STLCLR.dll /r:StlClrClassLibrary.dll /r:System.dll  
  
using System;  
using System.Collections.Generic;  
using StlClrClassLibrary;  
using cliext;  
  
namespace CsConsoleApp  
{  
    class Program  
    {  
        static int Main(string[] args)  
        {  
            StlClrClass theClass = new StlClrClass();  
  
            Console.WriteLine("cliext::deque contents:");  
            ICollection<char> iCollChar = theClass.GetDequeCs();  
            foreach (char c in iCollChar)  
            {  
                Console.WriteLine(c);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::list contents:");  
            ICollection<float> iCollFloat = theClass.GetListCs();  
            foreach (float f in iCollFloat)  
            {  
                Console.WriteLine(f);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::map contents:");  
            IDictionary<int, string> iDict = theClass.GetMapCs();  
            foreach (KeyValuePair<int, string> kvp in iDict)  
            {  
                Console.WriteLine("{0} {1}", kvp.Key, kvp.Value);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::set contents:");  
            ICollection<double> iCollDouble = theClass.GetSetCs();  
            foreach (double d in iCollDouble)  
            {  
                Console.WriteLine(d);  
            }  
            Console.WriteLine();  
  
            Console.WriteLine("cliext::vector contents:");  
            ICollection<int> iCollInt = theClass.GetVectorCs();  
            foreach (int i in iCollInt)  
            {  
                Console.WriteLine(i);  
            }  
            Console.WriteLine();  
  
            return 0;  
        }  
    }  
}  
```  
  
### Sortie  
  
```  
cliext::deque contents:  
a  
b  
  
cliext::list contents:  
3.14159  
2.71828  
  
cliext::map contents:  
0 Hello  
1 World  
  
cliext::set contents:  
2.71828  
3.14159  
  
cliext::vector contents:  
10  
20  
```  
  
## Voir aussi  
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)