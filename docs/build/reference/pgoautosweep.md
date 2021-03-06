---
title: PgoAutoSweep | Documents Microsoft
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- PgoAutoSweep
- PogoAutoSweepA
- PogoAutoSweepW
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 988a73dd8c4ad6929ef04691ad1959df7ea7bdd7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="pgoautosweep"></a>PgoAutoSweep

`PgoAutoSweep` enregistre les informations du compteur profil actuel dans un fichier et réinitialise les compteurs. Utilisez la fonction pendant l’apprentissage d’écrire un fichier .pgc utiliser ultérieurement lors de la génération de l’optimisation de toutes les données de profil à partir du programme en cours d’exécution de l’optimisation guidée par profil.

## <a name="syntax"></a>Syntaxe

```cpp
void PgoAutoSweep(const char* name);    // ANSI/MBCS
void PgoAutoSweep(const wchar_t* name); // UNICODE
```

### <a name="parameters"></a>Paramètres

*name*<br/>
Une chaîne d’identification pour le fichier .pgc enregistré.

## <a name="remarks"></a>Notes

Vous pouvez appeler `PgoAutoSweep` à partir de votre application pour enregistrer et réinitialiser les données de profil à tout moment au cours de l’exécution de l’application. Dans une version instrumentée, `PgoAutoSweep` capture les données de profilage actuelles, l’enregistre dans un fichier et réinitialise les compteurs de profil. Il est l’équivalent de l’appel de la [pgosweep](pgosweep.md) à un point spécifique dans votre fichier exécutable. Dans une version optimisée, `PgoAutoSweep` est une absence d’opération.

Les données de compteur de profil enregistré sont placées dans un fichier nommé *base_name*-*nom*! *valeur*.pgc, où *base_name* est le nom de base de l’exécutable, *nom* est le paramètre passé à `PgoAutoSweep`, et *valeur* est une valeur unique, généralement un nombre croissant, pour empêcher des collisions de nom de fichier.

Les fichiers .pgc créés par `PgoAutoSweep` doivent être fusionnés dans un fichier .pgd à utiliser pour créer un exécutable optimisé. Vous pouvez utiliser la [pgomgr](pgomgr.md) commande pour effectuer la fusion.

Vous pouvez passer le nom du fichier .pgd fusionnées à l’éditeur de liens lors de la génération d’optimisation à l’aide de la **PGD =**_nom de fichier_ l’argument de la [/useprofile](useprofile.md) option de l’éditeur de liens, ou par à l’aide de déconseillées **/PGD** option de l’éditeur de liens. Si vous fusionnez les fichiers .pgc dans un fichier nommé *base_name*.pgd, il est inutile de spécifier le nom de fichier sur la ligne de commande, car l’éditeur de liens récupère ce nom de fichier par défaut.

Le `PgoAutoSweep` fonction conserve le paramètre de sécurité des threads spécifié lorsque la génération instrumentée est créée. Si vous utilisez le paramètre par défaut ou spécifiez le **NOEXACT** l’argument de la [/GENPROFILE ou /fastgenprofile.]() option de l’éditeur de liens, les appels à `PgoAutoSweep` ne sont pas thread-safe. Le **EXACT** argument crée un thread-safe et plus précis, mais plus lente, instrumenté exécutable.

## <a name="requirements"></a>Spécifications

|Routine|En-tête requis|
|-------------|---------------------|
|`PgoAutoSweep`|\<pgobootrun.h >|

Le fichier exécutable doit inclure le fichier pgobootrun.lib dans les bibliothèques liées. Ce fichier est inclus dans votre installation de Visual Studio, dans le répertoire de bibliothèques VC pour chaque architecture prise en charge.

## <a name="example"></a>Exemple

L’exemple ci-dessous utilise `PgoAutoSweep` pour créer deux. Fichiers PGC à différents moments pendant l’exécution. La première ligne contient des données qui décrivent le comportement d’exécution jusqu'à ce que `count` est égal à 3, et le second contient les données collectées après ce point juste avant arrêt de l’application.

```cpp
// pgoautosweep.cpp
// Compile by using: cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp
// Link to instrument: link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj
// Run to generate data: pgoautosweep
// Merge data by using command line pgomgr tool:
// pgomgr /merge pgoautosweep-func1!1.pgc pgoautosweep-func2!1.pgc pgoautosweep.pgd
// Link to optimize: link /LTCG /useprofile pgobootrun.lib pgoautosweep.obj

#include <iostream>
#include <windows.h>
#include <pgobootrun.h>

void func2(int count)
{
    std::cout << "hello from func2 " << count << std::endl;
    Sleep(2000);
}

void func1(int count)
{
    std::cout << "hello from func1 " << count << std::endl;
    Sleep(2000);
}

int main()
{
    int count = 10;
    while (count--)
    {
        if (count < 3)
            func2(count);
        else
        {
            func1(count);
            if (count == 3)
            {
                PgoAutoSweep("func1");
            }
        }
    }
    PgoAutoSweep("func2");
}
```

Dans une invite de commandes développeur, compilez le code dans un fichier de l’objet à l’aide de cette commande :

`cl /c /GL /W4 /EHsc /O2 pgoautosweep.cpp`

Puis générer une version instrumentée pour l’apprentissage à l’aide de cette commande :

`link /LTCG /genprofile pgobootrun.lib pgoautosweep.obj`

Lancez l’exécutable instrumenté pour capturer les données d’apprentissage. La sortie des données par les appels à `PgoAutoSweep` est enregistré dans les fichiers nommés pgoautosweep-func1 ! 1.pgc et pgoautosweep-func2 ! 1.pgc. En cours d’exécution, la sortie du programme doit ressembler à ceci :

```Output
hello from func1 9
hello from func1 8
hello from func1 7
hello from func1 6
hello from func1 5
hello from func1 4
hello from func1 3
hello from func2 2
hello from func2 1
hello from func2 0
```

Fusionner les données enregistrées dans une base de données de formation de profil en exécutant la **pgomgr** commande :

`pgoautosweep-func1!1.pgc pgoautosweep-func2!1.pgc`

La sortie de cette commande ressemble à ceci :

```Output
Microsoft (R) Profile Guided Optimization Manager 14.13.26128.0
Copyright (C) Microsoft Corporation. All rights reserved.

Merging pgoautosweep-func1!1.pgc
pgoautosweep-func1!1.pgc: Used  3.8% (22304 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
Merging pgoautosweep-func2!1.pgc
pgoautosweep-func2!1.pgc: Used  3.8% (22424 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
```

Maintenant, vous pouvez utiliser ces données d’apprentissage pour générer une version optimisée. Cette commande permet de générer le fichier exécutable optimisé :

`link /LTCG /useprofile pgobootrun.lib pgoautosweep.obj`

```Output
Microsoft (R) Incremental Linker Version 14.13.26128.0
Copyright (C) Microsoft Corporation.  All rights reserved.

Merging pgoautosweep!1.pgc
pgoautosweep!1.pgc: Used  3.9% (22904 / 589824) of total space reserved.  0.0% of the counts were dropped due to overflow.
  Reading PGD file 1: pgoautosweep.pgd
Generating code

0 of 0 ( 0.0%) original invalid call sites were matched.
0 new call sites were added.
294 of 294 (100.00%) profiled functions will be compiled for speed
348 of 1239 inline instances were from dead/cold paths
294 of 294 functions (100.0%) were optimized using profile data
16870 of 16870 instructions (100.0%) were optimized using profile data
Finished generating code
```

## <a name="see-also"></a>Voir aussi

[Optimisations guidées par profil](profile-guided-optimizations.md)<br/>
[pgosweep](pgosweep.md)<br/>
