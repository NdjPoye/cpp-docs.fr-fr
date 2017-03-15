---
title: "Comment&#160;: convertir une collection .NET en conteneur STL/CLR | Microsoft Docs"
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
  - "STL/CLR, convertir à partir de collections .NET"
ms.assetid: bb927c48-78e8-4150-bd0b-787c651f4a87
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: convertir une collection .NET en conteneur STL/CLR
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique indique comment convertir des collections .NET vers les conteneurs STL\/CLR équivalents.  Comme exemple nous indiquons comment convertir un fournisseur .NET <xref:System.Collections.Generic.List%601> en un [vecteur](../dotnet/vector-stl-clr.md) STL\/CLR et comment convertir un fournisseur .NET <xref:System.Collections.Generic.Dictionary%602> en un [mappage](../dotnet/map-stl-clr.md) STL\/CLR , mais la procédure est similaire pour toutes les collections et conteneurs.  
  
### Pour créer un conteneur depuis une collection  
  
1.  Pour convertir une collection entière, créez un conteneur STL\/CLR et transmettez la collection au constructeur.  
  
     Le premier exemple montre cette procédure.  
  
 \- OU \-  
  
1.  Créez un conteneur STL\/CLR générique en créant un objet de [collection\_adapter](../dotnet/collection-adapter-stl-clr.md).  Cette classe de modèle prend une interface de collection .NET comme argument.  Pour vérifier quelles interfaces sont prises en charge, consultez [collection\_adapter](../dotnet/collection-adapter-stl-clr.md).  
  
2.  Copiez le contenu de la collection .NET dans le conteneur.  Cela peut être accompli en utilisant un [algorithme](../dotnet/algorithm-stl-clr.md) STL\/CLR, ou en itérant au sein de la collection .NET et en insérant une copie de chaque élément dans le conteneur STL ou CLR.  
  
     Cette procédure est illustrée dans le deuxième exemple.  
  
## Exemple  
 Dans cet exemple, nous créons un <xref:System.Collections.Generic.List%601> générique et ajoutons 5 éléments à celui\-ci.  Ensuite, nous créons un `vector` à l'aide du constructeur qui prend <xref:System.Collections.Generic.IEnumerable%601> comme argument.  
  
```  
// cliext_convert_list_to_vector.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/algorithm>  
#include <cliext/vector>  
  
using namespace System;  
using namespace System::Collections;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    List<int> ^primeNumbersColl = gcnew List<int>();  
    primeNumbersColl->Add(2);  
    primeNumbersColl->Add(3);  
    primeNumbersColl->Add(5);  
    primeNumbersColl->Add(7);  
    primeNumbersColl->Add(11);  
  
    cliext::vector<int> ^primeNumbersCont =  
        gcnew cliext::vector<int>(primeNumbersColl);  
  
    Console::WriteLine("The contents of the cliext::vector are:");  
    cliext::vector<int>::const_iterator it;  
    for (it = primeNumbersCont->begin(); it != primeNumbersCont->end(); it++)  
    {  
        Console::WriteLine(*it);  
    }  
}  
```  
  
  **Le contenu du cliext::vector est :**  
**2**  
**3**  
**5**  
**7**  
**11**   
## Exemple  
 Dans cet exemple, nous créons un <xref:System.Collections.Generic.Dictionary%602> générique et ajoutons 5 éléments à celui\-ci.  Ensuite, nous créons un `collection_adapter` pour encapsuler <xref:System.Collections.Generic.Dictionary%602> comme un simple conteneur STL\/CLR.  Enfin, nous créons un `map` et copions le contenu du <xref:System.Collections.Generic.Dictionary%602> dans `map` en l'itérant sur le `collection_adapter`.  Pendant ce processus, nous créons une nouvelle paire à l'aide de la fonction `make_pair`, et insérons les nouvelles paires directement dans `map`.  
  
```  
// cliext_convert_dictionary_to_map.cpp  
// compile with: /clr  
  
#include <cliext/adapter>  
#include <cliext/algorithm>  
#include <cliext/map>  
  
using namespace System;  
using namespace System::Collections;  
using namespace System::Collections::Generic;  
  
int main(array<System::String ^> ^args)  
{  
    System::Collections::Generic::Dictionary<float, int> ^dict =  
        gcnew System::Collections::Generic::Dictionary<float, int>();  
    dict->Add(42.0, 42);  
    dict->Add(13.0, 13);  
    dict->Add(74.0, 74);  
    dict->Add(22.0, 22);  
    dict->Add(0.0, 0);  
  
    cliext::collection_adapter<System::Collections::Generic::IDictionary<float, int>> dictAdapter(dict);  
    cliext::map<float, int> aMap;  
    for each (KeyValuePair<float, int> ^kvp in dictAdapter)  
    {  
        cliext::pair<float, int> aPair = cliext::make_pair(kvp->Key, kvp->Value);  
        aMap.insert(aPair);  
    }  
  
    Console::WriteLine("The contents of the cliext::map are:");  
    cliext::map<float, int>::const_iterator it;  
    for (it = aMap.begin(); it != aMap.end(); it++)  
    {  
        Console::WriteLine("Key: {0:F} Value: {1}", it->first, it->second);  
    }  
}  
```  
  
  **Le contenu du cliext::map est :**  
**Clé : 0.00 Valeur : 0**  
**Clé : 13.00 Valeur : 13**  
**Clé : 22.00 Valeur : 22**  
**Clé : 42.00 Valeur : 42**  
**Clé : 74.00 Valeur : 74**   
## Voir aussi  
 [STL\/CLR, bibliothèque](../dotnet/stl-clr-library-reference.md)   
 [adapter](../dotnet/adapter-stl-clr.md)   
 [Comment : convertir un conteneur STL\/CLR en collection .NET](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)