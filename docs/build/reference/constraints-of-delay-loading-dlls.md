---
title: "Contraintes relatives aux DLL &#224; chargement diff&#233;r&#233; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contraintes (C++), chargement différé de DLL"
  - "chargement différé de DLL, contraintes"
  - "DLL (C++), contraintes"
ms.assetid: 0097ff65-550f-4a4e-8ac3-39bf6404f926
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Contraintes relatives aux DLL &#224; chargement diff&#233;r&#233;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Des contraintes s'appliquent au chargement différé d'importations.  
  
-   Les importations de données ne peuvent pas être prises en charge.  Une solution de contournement consiste à ce que vous traitiez vous\-même explicitement l'importation de données en utilisant `LoadLibrary` \(ou `GetModuleHandle` une fois que vous savez que l'assistant de chargement différé a chargé la DLL\) et `GetProcAddress`.  
  
-   Le chargement différé de Kernel32.dll n'est pas pris en charge.  Cette DLL est nécessaire pour que les routines de l'assistant de chargement différé effectuent le chargement différé.  
  
-   La [liaison](../../build/reference/binding-imports.md) des points d'entrée qui sont transférés n'est pas prise en charge.  
  
-   Le chargement différé d'une DLL peut ne pas entraîner le même comportement du processus si des initialisations par processus surviennent au point d'entrée de la DLL chargée en différé.  D'autres cas incluent le stockage local des threads \(TLS\) de type statique, déclaré à l'aide de [\_\_declspec\(thread\)](../../cpp/thread.md), lequel n'est pas géré lorsque la DLL est chargée via `LoadLibrary`.  Le stockage local des threads \(TLS\) de type dynamique, via `TlsAlloc`, `TlsFree`, `TlsGetValue` et `TlsSetValue`, peut encore être utilisé dans les bibliothèques DLL statiques ou chargées en différé.  
  
-   Les pointeurs de fonction \(globaux\) statiques doivent être réinitialisés en fonctions importées après le premier appel à la fonction.  Cela est dû au fait que la première utilisation du pointeur de fonction pointera vers le thunk.  
  
-   Actuellement, il n'existe aucun moyen de différer le chargement de certaines procédures spécifiques seulement à partir d'une DLL tout en utilisant le mécanisme d'importation normal.  
  
-   Les conventions d'appel personnalisées \(telles que l'utilisation de codes de conditions sur les architectures x86\) ne sont pas prises en charge.  De plus, les registres à virgule flottante ne sont enregistrés sur aucune plateforme.  Si votre routine d'assistance personnalisée ou vos routines de hook utilisent des types à virgule flottante, elles doivent enregistrer et restaurer complètement l'état de virgule flottante sur les ordinateurs dotés de conventions d'appel de registre avec des paramètres à virgule flottante.  Soyez prudent avec le chargement différé de la DLL CRT si vous appelez des fonctions CRT qui acceptent des paramètres à virgule flottante sur une pile à coprocesseur arithmétique \(NDP\) dans la fonction d'aide.  
  
## Voir aussi  
 [Prise en charge de l'éditeur de liens pour les DLL à chargement différé](../../build/reference/linker-support-for-delay-loaded-dlls.md)   
 [LoadLibrary, fonction](http://msdn.microsoft.com/library/windows/desktop/ms684175.aspx)   
 [GetModuleHandle, fonction](http://msdn.microsoft.com/library/windows/desktop/ms683199.aspx)   
 [GetProcAddress, fonction](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx)   
 [TlsAlloc, fonction](http://msdn.microsoft.com/library/windows/desktop/ms686801.aspx)   
 [TlsFree, fonction](http://msdn.microsoft.com/library/windows/desktop/ms686804.aspx)   
 [TlsGetValue, fonction](http://msdn.microsoft.com/library/windows/desktop/ms686812.aspx)   
 [TlsSetValue, fonction](http://msdn.microsoft.com/library/windows/desktop/ms686818.aspx)