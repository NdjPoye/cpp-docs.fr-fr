---
title: "DLL en Visual C++ | Microsoft Docs"
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
  - "DLL (C++)"
  - "DLL (C++), à propos de DLL"
  - "liaison dynamique (C++)"
  - "fichiers exécutables (C++)"
  - "liaison (C++), comparaison entre dynamique et statique"
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# DLL en Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une bibliothèque de liens dynamiques \(DLL, Dynamic\-Link Library\) est un fichier exécutable qui sert de bibliothèque de fonctions et de ressources partagée.  La liaison dynamique permet à un fichier exécutable d'appeler des fonctions ou d'utiliser des ressources stockées dans un fichier séparé.  Ces fonctions et ressources peuvent être compilées et déployées séparément des exécutables qui les utilisent.  Le système d'exploitation peut charger la DLL dans l'espace mémoire de l'exécutable lors du chargement de l'exécutable, ou à la demande lors de l'exécution.  Les DLL facilitent également le partage des fonctions et des ressources entre les fichiers exécutables.  Plusieurs applications peuvent accéder simultanément au contenu d'une copie de la DLL en mémoire.  
  
 La liaison statique copie tout le code d'objet d'un fichier .lib dans un fichier exécutable.  La liaison dynamique inclut uniquement les informations nécessaires au moment de l'exécution pour localiser et charger la DLL qui contient un élément de données ou une fonction.  Quand vous créez une DLL, vous créez aussi un fichier .lib qui contient ces informations.  Quand vous générez un fichier exécutable qui appelle la DLL, l'éditeur de liens utilise les symboles exportés dans le fichier .lib pour stocker ces informations pour le chargeur.  Quand le chargeur charge une DLL, elle est mappée dans l'espace mémoire de votre exécutable.  Une fonction spéciale dans la DLL, `DllMain`, est appelée pour effectuer toute initialisation requise par la DLL.  
  
 Par rapport à la liaison statique, l'utilisation de la liaison dynamique offre plusieurs avantages.  Quand vous utilisez des DLL, vous pouvez économiser de l'espace mémoire et réduire l'échange.  Quand plusieurs applications peuvent utiliser une même copie d'une DLL, vous pouvez économiser de l'espace disque et de la bande passante.  Vous pouvez déployer et mettre à jour les DLL séparément, ce qui vous permet de fournir un support après\-vente et des mises à jour logicielles sans avoir à regénérer et à fournir tout votre code.  Les DLL constituent un moyen pratique de fournir des ressources spécifiques aux paramètres régionaux, qui peuvent prendre en charge les programmes multilingues, et elles facilitent la création de versions internationales de vos applications.  
  
 Les rubriques suivantes fournissent des informations détaillées sur la programmation des DLL.  
  
## Dans cette section  
 [Procédure pas à pas : création et utilisation d'une bibliothèque de liens dynamiques \(C\+\+\)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)  
 Montre comment créer et utiliser une DLL à l'aide de Visual Studio.  
  
 [Différences entre les applications et les DLL](../build/differences-between-applications-and-dlls.md)  
 Décrit les différences fondamentales existant entre les applications et les DLL.  
  
 [Avantages de l'utilisation des DLL](../build/advantages-of-using-dlls.md)  
 Décrit les avantages de la liaison dynamique.  
  
 [Genres de DLL](../build/kinds-of-dlls.md)  
 Fournit des informations sur les différentes sortes de DLL qui peuvent être générées.  
  
 [Forum Aux Questions à propos des DLL](../build/dll-frequently-asked-questions.md)  
 Fournit des réponses à des questions fréquentes concernant les DLL.  
  
 [Liaison d'un exécutable à une DLL](../build/linking-an-executable-to-a-dll.md)  
 Décrit la liaison explicite et implicite à une DLL.  
  
 [Initialisation d'une DLL](../build/initializing-a-dll.md)  
 Traite du code d'initialisation de la DLL \(comme l'allocation de mémoire\) qui doit s'exécuter lors du chargement de la DLL.  
  
 [Comportement de la bibliothèque Runtime](../build/run-time-library-behavior.md)  
 Décrit comment la bibliothèque Runtime exécute la séquence de démarrage de la DLL.  
  
 [LoadLibrary et AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
 Explique comment utiliser **LoadLibrary** et `AfxLoadLibrary` pour créer une liaison explicite à une DLL au moment de l'exécution.  
  
 [GetProcAddress](../build/getprocaddress.md)  
 Aborde l'utilisation de **GetProcAddress** pour obtenir l'adresse d'une fonction exportée dans la DLL.  
  
 [FreeLibrary et AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
 Traite de l'utilisation de **FreeLibrary** et de `AfxFreeLibrary` lorsque le module DLL n'est plus nécessaire.  
  
 [Chemin de recherche utilisé par Windows pour retrouver une DLL](../build/search-path-used-by-windows-to-locate-a-dll.md)  
 Décrit le chemin d'accès que le système d'exploitation Windows utilise pour rechercher une DLL sur le système.  
  
 [États du module d'une DLL normale liée de manière dynamique aux MFC](../build/module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)  
 Décrit les états du module d'une DLL normale liée de manière dynamique aux MFC.  
  
 [DLL d'extension](../build/extension-dlls-overview.md)  
 Décrit les DLL qui implémentent généralement des classes réutilisables dérivées de classes de bibliothèque MFC existantes.  
  
 [Création d'une DLL de ressource uniquement](../build/creating-a-resource-only-dll.md)  
 Traite des DLL de ressource uniquement, qui ne contiennent que des ressources, telles que des icônes, des images bitmap, des chaînes et des boîtes de dialogue.  
  
 [Ressources localisées dans les applications MFC : DLL satellites](../build/localized-resources-in-mfc-applications-satellite-dlls.md)  
 Fournit une prise en charge améliorée pour les DLL satellites, une fonctionnalité qui vous aide à créer des applications localisées pour différentes langues.  
  
 [Importation et exportation](../build/importing-and-exporting.md)  
 Décrit l'importation de symboles publics dans une application ou l'exportation de fonctions à partir d'une DLL.  
  
 [Technologie active et DLL](../build/active-technology-and-dlls.md)  
 Autorise l'implémentation des serveurs d'objets dans une DLL.  
  
 [Automation dans une DLL](../build/automation-in-a-dll.md)  
 Décrit ce que fournit l'option Automation de l'Assistant DLL MFC.  
  
 [Conventions d'affectation de noms pour les DLL MFC](../build/naming-conventions-for-mfc-dlls.md)  
 Décrit comment les DLL et les bibliothèques incluses dans les MFC obéissent aux règles d'une convention d'attribution de noms structurée.  
  
 [Appel de fonctions de la DLL à partir d'applications Visual Basic](../build/calling-dll-functions-from-visual-basic-applications.md)  
 Explique comment appeler des fonctions DLL à partir d'applications Visual Basic.  
  
## Rubriques connexes  
 [Utilisation de MFC dans le cadre d'une DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
 Décrit les DLL ordinaires, qui vous permettent d'utiliser la bibliothèque MFC dans une bibliothèque de liens dynamiques Windows.  
  
 [Version DLL de MFC](../mfc/tn033-dll-version-of-mfc.md)  
 Explique comment utiliser les bibliothèques de liens dynamiques partagées MFCxx.dll et MFCxxD.dll \(où x est le numéro de version MFC\) avec les applications MFC et les DLL d'extension.  
  
 [\(NOTINBUILD\)Visual C\+\+ Programming Methodologies](http://msdn.microsoft.com/fr-fr/0822f806-fa81-4b65-bf0f-1e2921f30c95)  
 Fournit des liens vers des rubriques qui fournissent des informations conceptuelles sur les bibliothèques Visual C\+\+ et des rubriques qui traitent des différentes technologies et techniques de codage.