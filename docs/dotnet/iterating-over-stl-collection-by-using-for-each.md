---
title: "It&#233;ration au sein d&#39;une collection STL en utilisant for each | Microsoft Docs"
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
  - "DTL (collections), itérer"
ms.assetid: 9358ca29-b982-4a19-bbfd-bef50fe66c9a
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# It&#233;ration au sein d&#39;une collection STL en utilisant for each
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le mot clé de `for each` peut être utilisé pour itérer sur une collection de bibliothèque C\+\+ standard \(STL\).  
  
## Toutes les plateformes  
 **Remarques**  
  
 Une collection de STL est également appelé *conteneur*.  Pour plus d'informations, consultez [Conteneurs STL](../standard-library/stl-containers.md).  
  
## Exemples  
 **Exemple**  
  
 L'exemple de code suivant utilise `for each` pour effectuer une itération au sein de [\< map \>](../standard-library/map.md).  
  
```  
// for_each_stl.cpp  
// compile with: /EHsc  
#include <map>  
#include <iostream>  
#include <string>  
using namespace std;  
  
int main() {  
   int retval  = 0;  
   map<string, int> months;  
  
   months["january"] = 31;  
   months["february"] = 28;  
   months["march"] = 31;  
   months["april"] = 30;  
   months["may"] = 31;  
   months["june"] = 30;  
   months["july"] = 31;  
   months["august"] = 31;  
   months["september"] = 30;  
   months["october"] = 31;  
   months["november"] = 30;  
   months["december"] = 31;  
  
   map<string, int> months_30;  
  
   for each( pair<string, int> c in months )  
      if ( c.second == 30 )  
         months_30[c.first] = c.second;  
  
   for each( pair<string, int> c in months_30 )  
      retval++;  
  
   cout << "Months with 30 days = " << retval << endl;  
}  
```  
  
 **Sortie**  
  
  **Mois de 30 jours \= 4** **Exemple**  
  
 L'exemple de code suivant utilise une référence const \(`const&`\) pour une variable d'itération avec les conteneurs de STL.  Vous pouvez utiliser une référence \(`&`\) en tant que variable d'itération sur toute collection d'un type qui peut être déclaré comme *T*`&`.  
  
```  
// for_each_stl_2.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
using namespace std;  
  
int main() {  
   int retval = 0;  
  
   vector<int> col(3);  
   col[0] = 10;  
   col[1] = 20;  
   col[2] = 30;  
  
   for each( const int& c in col )  
      retval += c;  
  
   cout << "retval: " << retval << endl;  
}  
```  
  
 **Sortie**  
  
  **retval: 60**   
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Remarques**  
  
 Il n'existe aucune note de plateforme spécifique sur cette fonctionnalité.  
  
### Conditions requises  
 Option du compilateur : **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Remarques**  
  
 Il n'existe aucune remarque de plateforme spécifique sur cette fonctionnalité.  
  
### Conditions requises  
 Option du compilateur : **\/clr**  
  
## Voir aussi  
 [for each, in](../dotnet/for-each-in.md)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)