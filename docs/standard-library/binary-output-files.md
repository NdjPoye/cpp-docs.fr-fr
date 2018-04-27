---
title: Fichiers de sortie binaires | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- I/O [C++], binary output files
- files [C++], binary output files
- binary data, binary output files
ms.assetid: 180954af-8cd6-444b-9a76-2f630a3389d8
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3456d410d0322f4843bc99b024ea0440ac1b93e8
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="binary-output-files"></a>Fichiers de sortie binaires

Les flux ont été conçus à l’origine pour le texte, par conséquent, le mode de sortie par défaut est le mode texte. En mode texte, le caractère de saut de ligne (10 hexadécimal) se développe en un retour chariot (16 bits uniquement). L’extension peut entraîner des problèmes, comme le montre ce qui suit :

```cpp
// binary_output_files.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };
int main( )
{
    ofstream os( "test.dat" );
    os.write( (char *) iarray, sizeof( iarray ) );
}
```

Vous pouvez vous attendre à ce que ce programme génère la séquence d’octets {99, 0, 10, 0} ; au lieu de cela, il génère {99, 0, 13, 10, 0}, ce qui entraîne des problèmes pour un programme qui attend une entrée binaire. Si vous avez besoin d’une véritable sortie binaire, dans laquelle les caractères sont écrits sans traduction, vous pouvez spécifier une sortie binaire à l’aide de l’argument openmode du constructeur [ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream) :

```cpp
// binary_output_files2.cpp
// compile with: /EHsc
#include <fstream>
using namespace std;
int iarray[2] = { 99, 10 };

int main()
{
   ofstream ofs ( "test.dat", ios_base::binary );

   // Exactly 8 bytes written
   ofs.write( (char*)&iarray[0], sizeof(int)*2 );
}
```

## <a name="see-also"></a>Voir aussi

[Flux de sortie](../standard-library/output-streams.md)<br/>
