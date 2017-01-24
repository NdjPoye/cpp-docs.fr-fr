---
title: "Comment&#160;: convertir un conteneur STL/CLR en collection .NET | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
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
  - "STL/CLR, convertir en collections .NET"
ms.assetid: 70b2dfd9-869c-4e0f-9a29-b1ee0cb0d107
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: convertir un conteneur STL/CLR en collection .NET
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique indique comment convertir des collections .NET vers les collections .NET équivalentes.  A titre d'exemple, nous vous montrons comment convertir un vecteur STL\/CLR [](../dotnet/vector-stl-clr.md "vector (STL-CLR)") vers un .NET <xref:System.Collections.Generic.ICollection%601> et comment convertir une map STL\/CLR [](../dotnet/map-stl-clr.md "map (STL-CLR)") vers une .NET <xref:System.Collections.Generic.IDictionary%602>, mais la procédure est similaire à toutes les collections et à tous les conteneurs.  
  
### Pour créer une collection depuis un conteneur  
  
1.  Utilisez l'une des méthodes suivantes :  
  
    -   Pour convertir une partie d'un conteneur, appelez la fonction [make\_collection](../dotnet/make-collection-stl-clr.md), puis passer l'itérateur de début et de fin l'itérateur du conteneur STL\/CLR à copier dans la collection.NET.  Cette fonction de modèle prend un itérateur de STL\/CLR comme argument TEMPLATE.  Le premier exemple montre cette méthode.  
  
    -   Pour convertir un conteneur entier, un cast le conteneur à une collection appropriée de l'interface de collecte ou d'interface.NET.  Le deuxième exemple illustre cette méthode.  
  
## Exemple  
 Dans cet exemple, nous créons un STL\/CLR `vector` générique et ajoutons 5 éléments à celui\-ci.  Ensuite, nous créons une collection de .NET en appelant la fonction de `make_collection`.  Enfin, nous affichons le contenu de la collection créée récemment.  
  
```  
// cliext_convert_vector_to_icollection.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/vector>  
  
using namespace cliext;  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    cliext::vector<int> primeNumbersCont;  
    primeNumbersCont.push_back(2);  
    primeNumbersCont.push_back(3);  
    primeNumbersCont.push_back(5);  
    primeNumbersCont.push_back(7);  
    primeNumbersCont.push_back(11);  
  
    System::Collections::Generic::ICollection<int> ^iColl =  
        make_collection<cliext::vector<int>::iterator>(  
            primeNumbersCont.begin() + 1,  
            primeNumbersCont.end() - 1);  
  
    Console::WriteLine("The contents of the System::Collections::Generic::ICollection are:");  
    for each (int i in iColl)  
    {  
        Console::WriteLine(i);  
    }  
}  
```  
  
  **Le contenu du System::Collections::Generic::ICollection est :**  
**3**  
**5**  
**7**   
## Exemple  
 Dans cet exemple, nous créons un STL\/CLR `map` générique et ajoutons 5 éléments à celui\-ci.  Ensuite, nous créons un fournisseur .NET <xref:System.Collections.Generic.IDictionary%602> et est affectons `map` directement.  Enfin, nous affichons le contenu de la collection créée récemment.  
  
```  
// cliext_convert_map_to_idictionary.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/map>  
  
using namespace cliext;  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    cliext::map<float, int> ^aMap = gcnew cliext::map<float, int>;  
    aMap->insert(cliext::make_pair<float, int>(42.0, 42));  
    aMap->insert(cliext::make_pair<float, int>(13.0, 13));  
    aMap->insert(cliext::make_pair<float, int>(74.0, 74));  
    aMap->insert(cliext::make_pair<float, int>(22.0, 22));  
    aMap->insert(cliext::make_pair<float, int>(0.0, 0));  
  
    System::Collections::Generic::IDictionary<float, int> ^iDict = aMap;  
  
    Console::WriteLine("The contents of the IDictionary are:");  
    for each (KeyValuePair<float, int> ^kvp in iDict)  
    {  
        Console::WriteLine("Key: {0:F} Value: {1}", kvp->Key, kvp->Value);  
    }  
}  
```  
  
  **Le contenu de l'IDictionary est :**  
**Clé : 0.00 Valeur : 0**  
**Clé : 13.00 Valeur : 13**  
**Clé : 22.00 Valeur : 22**  
**Clé : 42.00 Valeur : 42**  
**Clé : 74.00 Valeur : 74**   
## Voir aussi  
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)   
 [Comment : convertir une collection .NET en conteneur STL\/CLR](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)   
 [range\_adapter](../dotnet/range-adapter-stl-clr.md)