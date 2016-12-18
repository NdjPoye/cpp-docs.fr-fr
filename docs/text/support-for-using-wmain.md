---
title: "Prise en charge de l&#39;utilisation de wmain | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "wWinMain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "caractères larges (C++), wmain (fonction)"
  - "wmain (fonction)"
  - "wWinMain (fonction)"
ms.assetid: 41213c41-668c-40a4-8a1e-77d9eded720d
caps.latest.revision: 9
caps.handback.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Prise en charge de l&#39;utilisation de wmain
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ prend en charge la définition d'une fonction **wmain** et le passage d'arguments à caractère élargi à votre application Unicode.  Vous déclarez des paramètres formels à **wmain**, en utilisant un format identique à **main**.  Vous pouvez ensuite passer des arguments à caractère élargi et éventuellement un pointeur d'environnement à caractère élargi au programme.  Les paramètres `argv` et `envp` de la fonction **wmain** sont de type `wchar_t*`.  Par exemple :  
  
```  
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )  
```  
  
> [!NOTE]
>  Les applications Unicode MFC utilisent **wWinMain** comme point d'entrée.  Dans ce cas, `CWinApp::m_lpCmdLine` est une chaîne Unicode.  Veillez à définir **wWinMainCRTStartup** avec l'option de l'éditeur de liens [\/ENTRY](../build/reference/entry-entry-point-symbol.md).  
  
 Si votre programme utilise une fonction **main**, l'environnement de caractère multioctets est créé par la bibliothèque Runtime au démarrage du programme.  Une copie de l'environnement à caractère élargi est créée uniquement lorsqu'elle est nécessaire \(par exemple, par un appel des fonctions `_wgetenv` ou `_wputenv`\).  Au premier appel de `_wputenv`, ou de `_wgetenv` si un environnement MBCS existe déjà, un environnement de chaîne à caractère élargi correspondant est créé.  La variable globale `_wenviron` pointe vers l'environnement, elle est une version à caractère élargi de la variable globale `_environ`.  À ce moment\-là, deux copies de l'environnement \(MBCS et Unicode\) existent simultanément et sont conservées par le système d'exécution pendant toute la vie du programme.  
  
 De même, si votre programme utilise une fonction **wmain**, un environnement à caractère élargi est créé au moment du démarrage et une variable globale `_wenviron` pointe vers cet environnement.  Un environnement MBCS \(ASCII\) est créé au premier appel de `_putenv` ou `getenv`, et la variable globale `_environ` pointe vers cet environnement.  
  
## Voir aussi  
 [Prise en charge pour Unicode](../text/support-for-unicode.md)   
 [Synthèse de la programmation Unicode](../text/unicode-programming-summary.md)   
 [Fonction WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)