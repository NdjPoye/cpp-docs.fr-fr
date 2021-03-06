---
title: Construction d’objets de flux de sortie │ Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- output stream objects
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff3c924327c11d00dd9137a91ebd19ef7bdc9eaa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
---
# <a name="constructing-output-stream-objects"></a>Construction d'objets de flux de sortie

Si vous utilisez uniquement les objets prédéfinis `cout`, `cerr` ou `clog`, vous n’avez pas besoin de construire un flux de sortie. Vous devez utiliser des constructeurs pour les éléments suivants :

- [Constructeurs de flux de fichier de sortie](#vclrfoutputfilestreamconstructorsanchor1)

- [Constructeurs de flux de chaîne de sortie](#vclrfoutputstringstreamconstructorsanchor2)

## <a name="vclrfoutputfilestreamconstructorsanchor1"></a> Constructeurs de flux de fichier de sortie

Vous pouvez construire un flux de fichier de sortie de deux façons :

- Utilisez le constructeur par défaut, puis appelez la fonction membre `open`.

   ```cpp
   ofstream myFile; // Static or on the stack
   myFile.open("filename");

   ofstream* pmyFile = new ofstream; // On the heap
   pmyFile->open("filename");
   ```

- Spécifiez un nom de fichier et des indicateurs de mode dans l’appel du constructeur.

   ```cpp
   ofstream myFile("filename", ios_base::out);
   ```

## <a name="vclrfoutputstringstreamconstructorsanchor2"></a> Constructeurs de flux de chaîne de sortie

Pour construire un flux de chaîne de sortie, vous pouvez utiliser `ostringstream` de la façon suivante :

```cpp
using namespace std;
// ...
ostringstream myString;
myString << "this is a test" << ends;

string sp = myString.str(); // Obtain string
cout << sp << endl;
```

Le « manipulateur » `ends` ajoute le caractère null de fin nécessaire à la chaîne.

## <a name="see-also"></a>Voir aussi

[Flux de sortie](../standard-library/output-streams.md)<br/>
