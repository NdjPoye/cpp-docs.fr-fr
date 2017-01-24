---
title: "Conversion de projets du mode mixte en langage interm&#233;diaire pur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Intermediate Language (MSIL), applications en mode mixte"
  - "applications en mode mixte"
  - "applications en mode mixte, Intermediate Language (MSIL)"
  - "projets (C++), convertir en intermediate language"
ms.assetid: 855f9e3c-4f09-4bfe-8eab-a45f68292be9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Conversion de projets du mode mixte en langage interm&#233;diaire pur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Tous les projets CLR Visual C\+\+ sont liés par défaut aux bibliothèques Runtime C.  Par conséquent, ces projets sont classés comme applications en mode mixte, car ils contiennent à la fois du code natif et du code ayant pour cible le Common Language Runtime \(code managé\).  Ils sont compilés en langage intermédiaire \(IL, Intermediate Language\), également appelé MSIL \(Microsoft Intermediate Language\).  
  
### Pour convertir votre application en mode mixte en langage intermédiaire pur  
  
1.  Supprimez les liens aux [C Run\-Time Libraries](../c-runtime-library/crt-library-features.md) \(CRT\) :  
  
    1.  Dans le fichier .cpp définissant le point d'entrée de votre application, modifiez le point d'entrée en `Main()`.  L'utilisation de `Main()` indique que votre projet n'établit pas de liaison avec le CRT.  
  
    2.  Dans l'Explorateur de solutions, cliquez avec le bouton droit sur le projet et sélectionnez **Propriétés** dans le menu contextuel afin d'ouvrir les pages de propriétés de l'application.  
  
    3.  Dans la page de propriétés du projet **Avancé** pour l'**Éditeur de liens**, sélectionnez le champ **Point d'entrée** et saisissez **Main**.  
  
    4.  Pour les applications console, dans la page de propriétés du projet **Système** pour l'**Éditeur de liens**, sélectionnez le champ **Sous\-système** et changez son contenu en **Console \(\/SUBSYSTEM:CONSOLE\)**.  
  
        > [!NOTE]
        >  Il n'est pas nécessaire de définir cette propriété pour les applications Windows Forms parce que le champ **Sous\-système** contient par défaut la valeur **Windows \(\/SUBSYSTEM:WINDOWS\)**.  
  
    5.  Dans stdafx.h, transformez en commentaires toutes les instructions `#include`.  Par exemple, dans les applications console :  
  
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
  
    6.  Pour les applications Windows Forms, dans Form1.cpp, commentez l'instruction `#include` qui référence windows.h.  Par exemple :  
  
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
  
3.  Supprimez tous les types non managés :  
  
    1.  Le cas échéant, remplacez les types non managés par des références à des structures de l'espace de noms [System](https://msdn.microsoft.com/en-us/library/system.appdomainmanager.appdomainmanager.aspx).  Les types managés courants sont répertoriés dans le tableau suivant :  
  
        |Structure|Description|  
        |---------------|-----------------|  
        |[\<caps:sentence id\="tgt24" sentenceid\="84e2c64f38f78ba3ea5c905ab5a2da27" class\="tgtSentence"\>Boolean\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.boolean\(v=vs.140\).aspx)|Représente une valeur booléenne.|  
        |[\<caps:sentence id\="tgt26" sentenceid\="40ea57d3ee3c07bf1c102b466e1c3091" class\="tgtSentence"\>Byte\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.byte\(v=vs.140\).aspx)|Représente un entier non signé 8 bits.|  
        |[\<caps:sentence id\="tgt28" sentenceid\="a87deb01c5f539e6bda34829c8ef2368" class\="tgtSentence"\>Char\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.char\(v=vs.140\).aspx)|Représente un caractère Unicode.|  
        |[\<caps:sentence id\="tgt30" sentenceid\="dfeaaeb4316477bd556ea5e8c3295887" class\="tgtSentence"\>DateTime\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.datetime.datetime.aspx)|Représente un instant, généralement exprimé sous la forme d'une date ou d'une heure.|  
        |[\<caps:sentence id\="tgt32" sentenceid\="bdaa3c20a3e3851599514f7c6be5f62f" class\="tgtSentence"\>Décimal\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.decimal\(v=vs.140\).aspx)|Représente un nombre décimal.|  
        |[\<caps:sentence id\="tgt34" sentenceid\="e8cd7da078a86726031ad64f35f5a6c0" class\="tgtSentence"\>Double\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double\(v=vs.140\).aspx)|Représente un nombre à virgule flottante double précision.|  
        |[\<caps:sentence id\="tgt36" sentenceid\="1e0ca5b1252f1f6b1e0ac91be7e7219e" class\="tgtSentence"\>Guid\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.guid\(v=vs.140\).aspx)|Représente un GUID \(identificateur global unique\).|  
        |[\<caps:sentence id\="tgt38" sentenceid\="ce80d5ec65b1d2a2f1049eadc100db23" class\="tgtSentence"\>Int16\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.int16\(v=vs.140\).aspx)|Représente un entier signé 16 bits.|  
        |[\<caps:sentence id\="tgt40" sentenceid\="0241adbbd83925f051b694d40f02747f" class\="tgtSentence"\>Int32\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.int32\(v=vs.140\).aspx)|Représente un entier signé 32 bits.|  
        |[\<caps:sentence id\="tgt42" sentenceid\="ff9b3f96d37353c528517bc3656a00a8" class\="tgtSentence"\>Int64\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.int64\(v=vs.140\).aspx)|Représente un entier signé 64 bits.|  
        |[\<caps:sentence id\="tgt44" sentenceid\="7f1db863563907cf33604ed7fad6b111" class\="tgtSentence"\>IntPtr\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.intptr\(v=vs.140\).aspx)|Type spécifique à la plateforme, utilisé pour représenter un pointeur ou un handle.|  
        |[\<caps:sentence id\="tgt46" sentenceid\="943756eb7841efcc43b7cd37d7254c76" class\="tgtSentence"\>SByte\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.byte.aspx)|Représente un entier 8 bits signé.|  
        |[\<caps:sentence id\="tgt48" sentenceid\="dd5c07036f2975ff4bce568b6511d3bc" class\="tgtSentence"\>Single\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.single.aspx)|Représente un nombre à virgule flottante simple précision.|  
        |[\<caps:sentence id\="tgt50" sentenceid\="90150402997ea9c8dc45cc4d41bb28cb" class\="tgtSentence"\>Timespan\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.timespan\(v=vs.140\).aspx)|Représente un intervalle de temps.|  
        |[\<caps:sentence id\="tgt52" sentenceid\="a00ef2ef85ff67b7b39339886f19044f" class\="tgtSentence"\>UInt16\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uint16\(v=vs.140\).aspx)|Représente un entier non signé 16 bits.|  
        |[\<caps:sentence id\="tgt54" sentenceid\="3de84ad0700f2a1571f633d399e1900e" class\="tgtSentence"\>UInt32\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uint32\(v=vs.140\).aspx)|Représente un entier non signé 32 bits.|  
        |[\<caps:sentence id\="tgt56" sentenceid\="2e8d31865e5d4b9d8611e1b991baed07" class\="tgtSentence"\>UInt64\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uint64\(v=vs.140\).aspx)|Représente un entier non signé 64 bits.|  
        |[\<caps:sentence id\="tgt58" sentenceid\="92d74abda31865424016b16e2c806a66" class\="tgtSentence"\>UIntPtr\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uintptr\(v=vs.140\).aspx)|Type spécifique à la plateforme, utilisé pour représenter un pointeur ou un handle.|  
        |[\<caps:sentence id\="tgt60" sentenceid\="cab8111fd0b710a336c898e539090e34" class\="tgtSentence"\>Void\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.void\(v=vs.140\).aspx)|Indique une méthode qui ne retourne pas de valeur ; autrement dit, cette méthode a le type de retour void.|