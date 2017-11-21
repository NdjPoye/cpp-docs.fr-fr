---
title: "Conversion de projets à partir de Mode mixte au langage intermédiaire pur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- intermediate language, mixed-mode applications
- mixed-mode applications
- mixed-mode applications, intermediate language
- projects [C++], converting to intermediate language
ms.assetid: 855f9e3c-4f09-4bfe-8eab-a45f68292be9
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f59a90828f338d918f753c8ba79236fd7edc1587
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="converting-projects-from-mixed-mode-to-pure-intermediate-language"></a>Conversion de projets du mode mixte en langage intermédiaire pur
Tous les projets Visual C++ CLR lier aux bibliothèques Runtime C par défaut. Par conséquent, ces projets sont classés en tant que les applications en mode mixte, parce qu’elles combinent du code natif avec du code qui cible le common language runtime (code managé). Quand elles sont compilées, elles sont compilées en langage intermédiaire (IL), également appelé Microsoft intermediate langage MSIL.  
  
### <a name="to-convert-your-mixed-mode-application-into-pure-intermediate-language"></a>Pour convertir votre application en mode mixte en langage intermédiaire pur  
  
1.  Supprimer les liens vers les [les bibliothèques Runtime C](../c-runtime-library/crt-library-features.md) (CRT) :  
  
    1.  Dans le fichier .cpp définissant le point d’entrée de votre application, modifiez le point d’entrée `Main()`. À l’aide de `Main()` indique que votre projet ne contient pas de liens à la bibliothèque CRT.  
  
    2.  Dans l’Explorateur de solutions, cliquez sur votre projet et sélectionnez **propriétés** dans le menu contextuel pour ouvrir les pages de propriétés pour votre application.  
  
    3.  Dans le **avancé** page de propriétés de projet pour le **l’éditeur de liens**, sélectionnez le **Point d’entrée** , puis entrez **Main** dans ce champ.  
  
    4.  Pour les applications console, dans le **système** page de propriétés de projet pour le **l’éditeur de liens**, sélectionnez le **sous-système** champ et affecter à cette **Console (/ SUBSYSTEM:console)**.  
  
        > [!NOTE]
        >  Vous n’êtes pas obligé de définir cette propriété pour les applications Windows Forms, car le **sous-système** champ est défini sur **Windows (/ SUBSYSTEM : WINDOWS)** par défaut.  
  
    5.  Dans stdafx.h, commentez tout le `#include` instructions. Par exemple, dans les applications de console :  
  
        ```  
        // #include <iostream>  
        // #include <tchar.h>  
        ```  
  
         ou  
  
         Par exemple, dans les applications Windows Forms :  
  
        ```  
        // #include <stdlib.h>  
        // #include <malloc.h>  
        // #include <memory.h>  
        // #include <tchar.h>  
        ```  
  
    6.  Pour les applications Windows Forms, dans Form1.cpp, transformez en commentaire la `#include` instruction qui fait référence à windows.h. Exemple :  
  
        ```  
        // #include <windows.h>  
        ```  
  
2.  Ajoutez le code suivant à stdafx.h :  
  
    ```  
    #ifndef __FLTUSED__  
    #define __FLTUSED__  
       extern "C" __declspec(selectany) int _fltused=1;  
    #endif  
    ```  
  
3.  Supprimez tous les types managés en types :  
  
    1.  Le cas échéant, remplacez les types non managés par des références à des structures de la [système](https://msdn.microsoft.com/en-us/library/system.appdomainmanager.appdomainmanager.aspx) espace de noms. Les types managés courants sont répertoriés dans le tableau suivant :  
  
        |Structure|Description|  
        |---------------|-----------------|  
        |[Boolean](https://msdn.microsoft.com/en-us/library/system.boolean\(v=vs.140\).aspx)|Représente une valeur booléenne.|  
        |[Byte](https://msdn.microsoft.com/en-us/library/system.byte\(v=vs.140\).aspx)|Représente un entier non signé 8 bits.|  
        |[Char](https://msdn.microsoft.com/en-us/library/system.char\(v=vs.140\).aspx)|Représente un caractère Unicode.|  
        |[DateTime](https://msdn.microsoft.com/en-us/library/system.datetime.datetime.aspx)|Représente un instant, généralement exprimé sous la forme d'une date et d'une heure.|  
        |[Decimal](https://msdn.microsoft.com/en-us/library/system.decimal\(v=vs.140\).aspx)|Représente un nombre décimal.|  
        |[Double](https://msdn.microsoft.com/en-us/library/system.double\(v=vs.140\).aspx)|Représente un nombre à virgule flottante double précision.|  
        |[Guid](https://msdn.microsoft.com/en-us/library/system.guid\(v=vs.140\).aspx)|Représente un GUID (identificateur global unique).|  
        |[Int16](https://msdn.microsoft.com/en-us/library/system.int16\(v=vs.140\).aspx)|Représente un entier signé 16 bits.|  
        |[Int32](https://msdn.microsoft.com/en-us/library/system.int32\(v=vs.140\).aspx)|Représente un entier signé 32 bits.|  
        |[Int64](https://msdn.microsoft.com/en-us/library/system.int64\(v=vs.140\).aspx)|Représente un entier signé 64 bits.|  
        |[IntPtr](https://msdn.microsoft.com/en-us/library/system.intptr\(v=vs.140\).aspx)|Type spécifique à la plateforme, utilisé pour représenter un pointeur ou un handle.|  
        |[SByte](https://msdn.microsoft.com/en-us/library/system.byte.aspx)|Représente un entier 8 bits signé.|  
        |[Single](https://msdn.microsoft.com/en-us/library/system.single.aspx)|Représente un nombre à virgule flottante simple précision.|  
        |[TimeSpan](https://msdn.microsoft.com/en-us/library/system.timespan\(v=vs.140\).aspx)|Représente un intervalle de temps.|  
        |[UInt16](https://msdn.microsoft.com/en-us/library/system.uint16\(v=vs.140\).aspx)|Représente un entier non signé 16 bits.|  
        |[UInt32](https://msdn.microsoft.com/en-us/library/system.uint32\(v=vs.140\).aspx)|Représente un entier non signé 32 bits.|  
        |[UInt64](https://msdn.microsoft.com/en-us/library/system.uint64\(v=vs.140\).aspx)|Représente un entier non signé 64 bits.|  
        |[UIntPtr](https://msdn.microsoft.com/en-us/library/system.uintptr\(v=vs.140\).aspx)|Type spécifique à la plateforme, utilisé pour représenter un pointeur ou un handle.|  
        |[Void](https://msdn.microsoft.com/en-us/library/system.void\(v=vs.140\).aspx)|Indique une méthode qui ne retourne pas de valeur ; Autrement dit, la méthode a le type de retour void.|