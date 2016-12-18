---
title: "Comment&#160;: compiler du code MFC et ATL &#224; l&#39;aide de /clr | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr (option du compilateur C++), compiler du code ATL et MFC"
  - "ATL (C++), interopérabilité"
  - "DLL d'extension (C++), /clr (option du compilateur)"
  - "Interop (C++), /clr (option du compilateur)"
  - "interopérabilité (C++), /clr (option du compilateur)"
  - "MFC (C++), interopérabilité"
  - "assemblys mixtes (C++), ATL (code)"
  - "assemblys mixtes (C++), MFC (code)"
  - "DLL normales (C++), /clr (option du compilateur)"
ms.assetid: 12464bec-33a4-482c-880a-c078de7f6ea5
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: compiler du code MFC et ATL &#224; l&#39;aide de /clr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique comment compiler des programmes MFC et ATL existants pour cibler le Common Language Runtime.  
  
### Pour compiler un exécutable MFC ou une DLL régulière à l'aide de \/clr  
  
1.  Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le projet, puis cliquez sur **Propriétés**.  
  
2.  Dans la boîte de dialogue **Propriétés du projet**, développez le nœud **Propriétés de configuration** et sélectionnez **Général**.  Dans le volet droit, sous **Paramètres par défaut du projet**, affectez à **Prise en charge du Common Language Runtime** la valeur **Common Language Runtime Support \(\/clr\)**.  
  
     Dans le même volet, assurez\-vous que **Utilisation des MFC** est défini sur **Utiliser les MFC dans une DLL partagée**.  
  
3.  Sous **Propriétés de configuration**, développez le nœud à côté de **C\/C\+\+** et sélectionnez **Général**.  Assurez\-vous que **Format des informations de débogage** est configuré sur **Program Database \/Zi** \(et non **\/ZI**\).  
  
4.  Sélectionnez le nœud **Génération de code**.  Affectez à **Activation de la régénération minimale** la valeur **Non \(\/Gm\-\)**.  Attribuez également à **Vérifications de base à l'exécution** la valeur **Par défaut**.  
  
5.  Sous **Propriétés de configuration**, sélectionnez **C\/C\+\+**, puis **Génération de code**.  Assurez\-vous que **Bibliothèque Runtime** a pour valeur **DLL de débogage multithread \(\/MDd\)** ou **DLL multithread \(\/MD\)**.  
  
6.  Dans Stdafx.h, ajoutez le code suivant :  
  
    ```  
    #using <System.Windows.Forms.dll>  
    ```  
  
### Pour compiler une DLL d'extension MFC à l'aide de \/clr  
  
1.  Suivez les étapes décrites dans « Pour compiler un exécutable MFC ou une DLL régulière à l'aide de \/clr ».  
  
2.  Sous **Propriétés de configuration**, développez le nœud à côté de **C\/C\+\+** et sélectionnez **En\-têtes précompilés**.  Attribuez à **Création\/utilisation d'un en\-tête précompilé** la valeur **Sans utiliser les en\-têtes précompilés**.  
  
     Vous pouvez également cliquer avec le bouton droit dans l'**Explorateur de solutions** sur Stdafx.cpp, puis cliquer sur **Propriétés**.  Sous **Propriétés de configuration**, développez le nœud à côté de **C\/C\+\+** et sélectionnez **Général**.  Affectez à **Compilation avec prise en charge du Common Language Runtime** la valeur **Pas de prise en charge du Common Language Runtime**.  
  
3.  Pour le fichier qui contient DllMain et tout élément qu'il appelle, dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le fichier puis cliquez sur **Propriétés**.  Sous **Propriétés de configuration**, développez le nœud à côté de **C\/C\+\+** et sélectionnez **Général**.  Dans le volet droit, sous **Paramètres par défaut du projet**, affectez à **Compilation avec prise en charge du Common Language Runtime** la valeur **Pas de prise en charge du Common Language Runtime Support**.  
  
### Pour compiler un exécutable ATL à l'aide de \/clr  
  
1.  Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le projet, puis cliquez sur **Propriétés**.  
  
2.  Dans la boîte de dialogue **Propriétés du projet**, développez le nœud **Propriétés de configuration** et sélectionnez **Général**.  Dans le volet droit, sous **Paramètres par défaut du projet**, affectez à **Prise en charge du Common Language Runtime** la valeur **Common Language Runtime Support \(\/clr\)**.  
  
3.  Sous **Propriétés de configuration**, développez le nœud à côté de **C\/C\+\+** et sélectionnez **Général**.  Assurez\-vous que **Format des informations de débogage** est configuré sur **Program Database \/Zi** \(et non **\/ZI**\).  
  
4.  Sélectionnez le nœud **Génération de code**.  Affectez à **Activation de la régénération minimale** la valeur **Non \(\/Gm\-\)**.  Attribuez également à **Vérifications de base à l'exécution** la valeur **Par défaut**.  
  
5.  Sous **Propriétés de configuration**, sélectionnez **C\/C\+\+**, puis **Génération de code**.  Assurez\-vous que **Bibliothèque Runtime** a pour valeur **DLL de débogage multithread \(\/MDd\)** ou **DLL multithread \(\/MD\)**.  
  
6.  Pour chaque fichier généré par le compilateur MIDL \(fichiers C\), cliquez avec le bouton droit sur le fichier dans l'**Explorateur de solutions** puis cliquez sur **Propriétés**.  Sous **Propriétés de configuration**, développez le nœud à côté de **C\/C\+\+** et sélectionnez **Général**.  Affectez à **Compilation avec prise en charge du Common Language Runtime** la valeur **Pas de prise en charge du Common Language Runtime**.  
  
### Pour compiler une DLL ATL à l'aide de \/clr  
  
1.  Suivez les étapes décrites dans la section « Pour compiler un exécutable ATL à l'aide de \/clr ».  
  
2.  Sous **Propriétés de configuration**, développez le nœud à côté de **C\/C\+\+** et sélectionnez **En\-têtes précompilés**.  Attribuez à **Création\/utilisation d'un en\-tête précompilé** la valeur **Sans utiliser les en\-têtes précompilés**.  
  
     Vous pouvez également cliquer avec le bouton droit dans l'**Explorateur de solutions** sur Stdafx.cpp, puis cliquer sur **Propriétés**.  Sous **Propriétés de configuration**, développez le nœud à côté de **C\/C\+\+** et sélectionnez **Général**.  Affectez à **Compilation avec prise en charge du Common Language Runtime** la valeur **Pas de prise en charge du Common Language Runtime**.  
  
3.  Pour le fichier qui contient DllMain et tout élément qu'il appelle, dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur le fichier puis cliquez sur **Propriétés**.  Sous **Propriétés de configuration**, développez le nœud à côté de **C\/C\+\+** et sélectionnez **Général**.  Dans le volet droit, sous **Paramètres par défaut du projet**, affectez à **Compilation avec prise en charge du Common Language Runtime** la valeur **Pas de prise en charge du Common Language Runtime Support**.  
  
## Voir aussi  
 [Assemblys mixtes \(natif et managé\)](../dotnet/mixed-native-and-managed-assemblies.md)