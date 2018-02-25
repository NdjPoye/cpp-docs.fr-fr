---
title: "Construction d’objets de flux de sortie │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- output stream objects
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf40e6683462803fcf81a9be915a4672baefd3e9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="constructing-output-stream-objects"></a>Construction d'objets de flux de sortie
Si vous utilisez uniquement les objets prédéfinis `cout`, `cerr` ou `clog`, vous n’avez pas besoin de construire un flux de sortie. Vous devez utiliser des constructeurs pour les éléments suivants :  
  
- [Constructeurs de flux de fichier de sortie](#vclrfoutputfilestreamconstructorsanchor1)  
  
- [Constructeurs de flux de chaîne de sortie](#vclrfoutputstringstreamconstructorsanchor2)  
  
##  <a name="vclrfoutputfilestreamconstructorsanchor1"></a> Constructeurs de flux de fichier de sortie  
 Vous pouvez construire un flux de fichier de sortie de deux façons :  
  
-   Utilisez le constructeur par défaut, puis appelez la fonction membre `open`.  
  
 ```  
    ofstream myFile; // Static or on the stack  
    myFile.open("filename");

 
    ofstream* pmyFile = new ofstream; // On the heap  
    pmyFile->open("filename");
```  
  
-   Spécifiez un nom de fichier et des indicateurs de mode dans l’appel du constructeur.  
  
 ```  
    ofstream myFile("filename", ios_base::out);
```  
  
##  <a name="vclrfoutputstringstreamconstructorsanchor2"></a> Constructeurs de flux de chaîne de sortie  
 Pour construire un flux de chaîne de sortie, vous pouvez utiliser `ostringstream` de la façon suivante :  
  
```  
    using namespace std;  
string sp;  
ostringstream myString;  
myString <<"this is a test" <<ends;  
sp = myString.str();
// Obtain string  
cout <<sp <endl;   
```  
  
 Le « manipulateur » `ends` ajoute le caractère null de fin nécessaire à la chaîne.  
  
## <a name="see-also"></a>Voir aussi  
 [Flux de sortie](../standard-library/output-streams.md)

