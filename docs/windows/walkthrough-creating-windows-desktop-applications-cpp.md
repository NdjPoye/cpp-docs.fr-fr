---
title: "Proc&#233;dure pas &#224; pas&#160;: cr&#233;ation d’applications de bureau Windows (C++) | Microsoft Docs"
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
  - "applications Windows [C++], Win32"
  - "WinMain"
  - "applications Win32 (C++)"
  - "API Windows (C++)"
ms.assetid: a247a9af-aff1-4899-9577-5f8104a0afbb
caps.latest.revision: 27
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: cr&#233;ation d’applications de bureau Windows (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette procédure pas à pas montre comment créer une application de bureau Windows de base qui affiche « Hello, World\! » dans une fenêtre. Vous pouvez utiliser le code que vous développez dans cette procédure pas à pas comme modèle pour créer d’autres applications de bureau Windows.  
  
 L’API Win32 \(également appelée API Windows\) est une infrastructure basée sur C pour créer des applications Windows. Pour plus d’informations sur l’API Win32, consultez [API Windows](https://msdn.microsoft.com/en-us/library/cc433218.aspx).  
  
> [!IMPORTANT]
>  Afin d’expliquer plus clairement certains segments de code lors des différentes étapes de ce document, nous pouvons omettre certaines instructions de code qui sont normalement obligatoires pour qu’une application fonctionne \(par exemple des directives include et des déclarations de variables globales\). La section **Exemple** à la fin de ce document présente le code complet.  
  
## Composants requis  
 Pour compléter cette procédure pas à pas, vous devez comprendre les notions de base du langage C\+\+.  
  
 Pour obtenir une démonstration vidéo, consultez la page [Video How to: Creating Win32 Applications \(C\+\+\)](http://go.microsoft.com/fwlink/?LinkId=102471) dans la documentation de Visual Studio 2008.  
  
### Pour créer un projet Win32  
  
1.  Dans le menu **Fichier**, cliquez sur **Nouveau**, puis sur **Projet**.  
  
2.  Dans la boîte de dialogue **Nouveau projet**, dans le volet gauche, cliquez sur **Modèles installés**, sur **Visual C\+\+**, puis sélectionnez **Win32**. Dans le volet central, sélectionnez **Projet Win32**.  
  
     Dans la zone **Nom**, tapez le nom du projet, par exemple `win32app`. Cliquez sur **OK**.  
  
3.  Dans la page d’accueil de l’**Assistant Application Win32**, cliquez sur **Suivant**.  
  
4.  Dans la page Paramètres de l’application sous **Type d’application**, sélectionnez **Application Windows**. Sous **Options supplémentaires**, sélectionnez **Projet vide**. Cliquez sur **Terminer** pour créer le projet.  
  
5.  Dans l’**Explorateur de solutions**, cliquez avec le bouton droit sur le projet Win32app, cliquez sur **Ajouter**, puis sur **Nouvel élément**. Dans la boîte de dialogue **Ajouter un nouvel élément**, sélectionnez **Fichier C\+\+ \(.cpp\)**. Dans la zone **Nom**, tapez un nom pour le fichier, par exemple `GT_HelloWorldWin32.cpp`. Cliquez sur **Ajouter**.  
  
### Pour démarrer une application de bureau Windows  
  
1.  Tout comme chaque application C et C\+\+ doit avoir une fonction `main` comme point de départ, toutes les applications Win32 doivent avoir une fonction `WinMain`. La syntaxe de `WinMain` est la suivante.  
  
    ```  
    int WINAPI WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nCmdShow);  
    ```  
  
     Pour plus d’informations sur les paramètres et la valeur de retour de cette fonction, consultez [Fonction WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559).  
  
2.  Étant donné que le code d’application doit utiliser des définitions existantes, ajoutez des instructions include au fichier.  
  
    ```  
    #include <windows.h> #include <stdlib.h> #include <string.h> #include <tchar.h>  
    ```  
  
3.  Outre la fonction `WinMain`, chaque application de bureau Windows doit avoir une fonction de procédure de fenêtre. Cette fonction se nomme généralement `WndProc`. La syntaxe de `WndProc` est la suivante.  
  
    ```  
    LRESULT CALLBACK WndProc(HWND, UINT, WPARAM, LPARAM);  
    ```  
  
     Cette fonction traite les nombreux *messages* qu’une application reçoit en provenance du système d’exploitation. Par exemple, dans une application qui possède une boîte de dialogue avec un bouton **OK**, lorsque l’utilisateur clique sur ce bouton, le système d’exploitation envoie à l’application un message signalant le clic sur bouton.`WndProc` est chargée de répondre à cet événement. Dans l’exemple, la réponse appropriée peut être la fermeture de la boîte de dialogue.  
  
     Pour plus d’informations, consultez [Window Procedures](http://msdn.microsoft.com/library/windows/desktop/ms632593).  
  
### Pour ajouter une fonctionnalité à la fonction WinMain  
  
1.  Dans la fonction `WinMain`, créez une structure de classe de fenêtre de type [WNDCLASSEX](http://msdn.microsoft.com/library/windows/desktop/ms633577). Cette structure contient des informations sur la fenêtre, par exemple l’icône de l’application, la couleur d’arrière\-plan de la fenêtre, le nom à afficher dans la barre de titre, le nom de la fonction de procédure de fenêtre, et ainsi de suite. L’exemple suivant montre une structure `WNDCLASSEX` type.  
  
    ```  
    WNDCLASSEX wcex; wcex.cbSize = sizeof(WNDCLASSEX); wcex.style          = CS_HREDRAW | CS_VREDRAW; wcex.lpfnWndProc    = WndProc; wcex.cbClsExtra     = 0; wcex.cbWndExtra     = 0; wcex.hInstance      = hInstance; wcex.hIcon          = LoadIcon(hInstance, MAKEINTRESOURCE(IDI_APPLICATION)); wcex.hCursor        = LoadCursor(NULL, IDC_ARROW); wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1); wcex.lpszMenuName   = NULL; wcex.lpszClassName  = szWindowClass; wcex.hIconSm        = LoadIcon(wcex.hInstance, MAKEINTRESOURCE(IDI_APPLICATION));  
    ```  
  
     Pour plus d’informations sur les champs de cette structure, consultez [WNDCLASSEX](http://msdn.microsoft.com/library/windows/desktop/ms633577).  
  
2.  Maintenant que vous avez créé une classe de fenêtre, vous devez l’inscrire. Utilisez la fonction [RegisterClassEx](http://msdn.microsoft.com/library/windows/desktop/ms633587) et passez la structure de classe de fenêtre comme argument.  
  
    ```  
    if (!RegisterClassEx(&wcex)) { MessageBox(NULL, _T("Call to RegisterClassEx failed!"), _T("Win32 Guided Tour"), NULL); return 1; }  
    ```  
  
3.  Vous pouvez maintenant créer une fenêtre. Utilisez la fonction [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679).  
  
    ```  
    static TCHAR szWindowClass[] = _T("win32app"); static TCHAR szTitle[] = _T("Win32 Guided Tour Application"); // The parameters to CreateWindow explained: // szWindowClass: the name of the application // szTitle: the text that appears in the title bar // WS_OVERLAPPEDWINDOW: the type of window to create // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y) // 500, 100: initial size (width, length) // NULL: the parent of this window // NULL: this application does not have a menu bar // hInstance: the first parameter from WinMain // NULL: not used in this application HWND hWnd = CreateWindow( szWindowClass, szTitle, WS_OVERLAPPEDWINDOW, CW_USEDEFAULT, CW_USEDEFAULT, 500, 100, NULL, NULL, hInstance, NULL ); if (!hWnd) { MessageBox(NULL, _T("Call to CreateWindow failed!"), _T("Win32 Guided Tour"), NULL); return 1; }  
    ```  
  
     Cette fonction retourne un HWND, qui est un handle de fenêtre. Pour plus d'informations, consultez [Types de données Windows](http://msdn.microsoft.com/library/windows/desktop/aa383751).  
  
4.  Utilisez maintenant le code suivant pour afficher la fenêtre.  
  
    ```  
    // The parameters to ShowWindow explained: // hWnd: the value returned from CreateWindow // nCmdShow: the fourth parameter from WinMain ShowWindow(hWnd, nCmdShow); UpdateWindow(hWnd);  
    ```  
  
     À ce stade, la fenêtre affichée ne contient pas grand chose car vous n’avez pas encore implémenté la fonction `WndProc`.  
  
5.  Maintenant, ajoutez une boucle de message pour écouter les messages envoyés par le système d’exploitation. Lorsque l’application reçoit un message, cette boucle l’envoie à la fonction `WndProc` pour qu’il soit traité. La boucle de message ressemble au code suivant.  
  
    ```  
    MSG msg; while (GetMessage(&msg, NULL, 0, 0)) { TranslateMessage(&msg); DispatchMessage(&msg); } return (int) msg.wParam;  
    ```  
  
     Pour plus d’informations sur les structures et les fonctions dans la boucle de message, consultez [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958), [GetMessage](http://msdn.microsoft.com/library/windows/desktop/ms644936), [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).  
  
     À ce stade, la fonction `WinMain` doit ressembler au code suivant.  
  
    ```  
    int WINAPI WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nCmdShow) { WNDCLASSEX wcex; wcex.cbSize = sizeof(WNDCLASSEX); wcex.style          = CS_HREDRAW | CS_VREDRAW; wcex.lpfnWndProc    = WndProc; wcex.cbClsExtra     = 0; wcex.cbWndExtra     = 0; wcex.hInstance      = hInstance; wcex.hIcon          = LoadIcon(hInstance, MAKEINTRESOURCE(IDI_APPLICATION)); wcex.hCursor        = LoadCursor(NULL, IDC_ARROW); wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1); wcex.lpszMenuName   = NULL; wcex.lpszClassName  = szWindowClass; wcex.hIconSm        = LoadIcon(wcex.hInstance, MAKEINTRESOURCE(IDI_APPLICATION)); if (!RegisterClassEx(&wcex)) { MessageBox(NULL, _T("Call to RegisterClassEx failed!"), _T("Win32 Guided Tour"), NULL); return 1; } hInst = hInstance; // Store instance handle in our global variable // The parameters to CreateWindow explained: // szWindowClass: the name of the application // szTitle: the text that appears in the title bar // WS_OVERLAPPEDWINDOW: the type of window to create // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y) // 500, 100: initial size (width, length) // NULL: the parent of this window // NULL: this application dows not have a menu bar // hInstance: the first parameter from WinMain // NULL: not used in this application HWND hWnd = CreateWindow( szWindowClass, szTitle, WS_OVERLAPPEDWINDOW, CW_USEDEFAULT, CW_USEDEFAULT, 500, 100, NULL, NULL, hInstance, NULL ); if (!hWnd) { MessageBox(NULL, _T("Call to CreateWindow failed!"), _T("Win32 Guided Tour"), NULL); return 1; } // The parameters to ShowWindow explained: // hWnd: the value returned from CreateWindow // nCmdShow: the fourth parameter from WinMain ShowWindow(hWnd, nCmdShow); UpdateWindow(hWnd); // Main message loop: MSG msg; while (GetMessage(&msg, NULL, 0, 0)) { TranslateMessage(&msg); DispatchMessage(&msg); } return (int) msg.wParam; }  
    ```  
  
### Pour ajouter une fonctionnalité à la fonction WndProc  
  
1.  Pour permettre à la fonction `WndProc` de traiter les messages reçus par l’application, implémentez une instruction switch.  
  
     Le premier message à traiter est le message [WM\_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213). L’application reçoit ce message quand une partie de sa fenêtre affichée doit être mise à jour. \(Lors de l’affichage initial de la fenêtre, tout son contenu doit être mis à jour.\)  
  
     Pour traiter un message `WM_PAINT`, appelez d’abord [BeginPaint](http://msdn.microsoft.com/library/windows/desktop/dd183362), puis traitez toute la logique pour disposer le texte, les boutons et autres contrôles dans la fenêtre, puis appelez [EndPaint](http://msdn.microsoft.com/library/windows/desktop/dd162598). Pour cette application, la logique entre l’appel de début et l’appel de fin consiste à afficher la chaîne « Hello, World\! » dans la fenêtre. Dans le code suivant, notez que la fonction [TextOut](http://msdn.microsoft.com/library/windows/desktop/dd145133) est utilisée pour afficher la chaîne.  
  
    ```  
    PAINTSTRUCT ps; HDC hdc; TCHAR greeting[] = _T("Hello, World!"); switch (message) { case WM_PAINT: hdc = BeginPaint(hWnd, &ps); // Here your application is laid out. // For this introduction, we just print out "Hello, World!" // in the top left corner. TextOut(hdc, 5, 5, greeting, _tcslen(greeting)); // End application-specific layout section. EndPaint(hWnd, &ps); break; }  
    ```  
  
2.  Une application traite généralement beaucoup d’autres messages, par exemple [WM\_CREATE](http://msdn.microsoft.com/library/windows/desktop/ms632619) et [WM\_DESTROY](http://msdn.microsoft.com/library/windows/desktop/ms632620). Le code suivant illustre une fonction `WndProc` basique mais complète.  
  
    ```  
    LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam) { PAINTSTRUCT ps; HDC hdc; TCHAR greeting[] = _T("Hello, World!"); switch (message) { case WM_PAINT: hdc = BeginPaint(hWnd, &ps); // Here your application is laid out. // For this introduction, we just print out "Hello, World!" // in the top left corner. TextOut(hdc, 5, 5, greeting, _tcslen(greeting)); // End application specific layout section. EndPaint(hWnd, &ps); break; case WM_DESTROY: PostQuitMessage(0); break; default: return DefWindowProc(hWnd, message, wParam, lParam); break; } return 0; }  
    ```  
  
##  <a name="example"></a> Exemple  
  
#### Pour générer cet exemple  
  
1.  Créez un projet Win32 comme indiqué plus haut dans « Pour créer un projet Win32 » dans cette procédure pas à pas.  
  
2.  Copiez le code qui suit ces étapes et collez\-le dans le fichier source GT\_HelloWorldWin32.cpp.  
  
3.  Dans le menu **Générer**, cliquez sur **Générer la solution**.  
  
4.  Pour exécuter l’application, appuyez sur F5. Une fenêtre qui contient le texte « Hello World\! » doit apparaître dans le coin supérieur gauche de l’affichage.  
  
### Code  
  
```  
// GT_HelloWorldWin32.cpp // compile with: /D_UNICODE /DUNICODE /DWIN32 /D_WINDOWS /c #include <windows.h> #include <stdlib.h> #include <string.h> #include <tchar.h> // Global variables // The main window class name. static TCHAR szWindowClass[] = _T("win32app"); // The string that appears in the application's title bar. static TCHAR szTitle[] = _T("Win32 Guided Tour Application"); HINSTANCE hInst; // Forward declarations of functions included in this code module: LRESULT CALLBACK WndProc(HWND, UINT, WPARAM, LPARAM); int WINAPI WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nCmdShow) { WNDCLASSEX wcex; wcex.cbSize = sizeof(WNDCLASSEX); wcex.style          = CS_HREDRAW | CS_VREDRAW; wcex.lpfnWndProc    = WndProc; wcex.cbClsExtra     = 0; wcex.cbWndExtra     = 0; wcex.hInstance      = hInstance; wcex.hIcon          = LoadIcon(hInstance, MAKEINTRESOURCE(IDI_APPLICATION)); wcex.hCursor        = LoadCursor(NULL, IDC_ARROW); wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1); wcex.lpszMenuName   = NULL; wcex.lpszClassName  = szWindowClass; wcex.hIconSm        = LoadIcon(wcex.hInstance, MAKEINTRESOURCE(IDI_APPLICATION)); if (!RegisterClassEx(&wcex)) { MessageBox(NULL, _T("Call to RegisterClassEx failed!"), _T("Win32 Guided Tour"), NULL); return 1; } hInst = hInstance; // Store instance handle in our global variable // The parameters to CreateWindow explained: // szWindowClass: the name of the application // szTitle: the text that appears in the title bar // WS_OVERLAPPEDWINDOW: the type of window to create // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y) // 500, 100: initial size (width, length) // NULL: the parent of this window // NULL: this application does not have a menu bar // hInstance: the first parameter from WinMain // NULL: not used in this application HWND hWnd = CreateWindow( szWindowClass, szTitle, WS_OVERLAPPEDWINDOW, CW_USEDEFAULT, CW_USEDEFAULT, 500, 100, NULL, NULL, hInstance, NULL ); if (!hWnd) { MessageBox(NULL, _T("Call to CreateWindow failed!"), _T("Win32 Guided Tour"), NULL); return 1; } // The parameters to ShowWindow explained: // hWnd: the value returned from CreateWindow // nCmdShow: the fourth parameter from WinMain ShowWindow(hWnd, nCmdShow); UpdateWindow(hWnd); // Main message loop: MSG msg; while (GetMessage(&msg, NULL, 0, 0)) { TranslateMessage(&msg); DispatchMessage(&msg); } return (int) msg.wParam; } // //  FUNCTION: WndProc(HWND, UINT, WPARAM, LPARAM) // //  PURPOSE:  Processes messages for the main window. // //  WM_PAINT    - Paint the main window //  WM_DESTROY  - post a quit message and return // // LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam) { PAINTSTRUCT ps; HDC hdc; TCHAR greeting[] = _T("Hello, World!"); switch (message) { case WM_PAINT: hdc = BeginPaint(hWnd, &ps); // Here your application is laid out. // For this introduction, we just print out "Hello, World!" // in the top left corner. TextOut(hdc, 5, 5, greeting, _tcslen(greeting)); // End application-specific layout section. EndPaint(hWnd, &ps); break; case WM_DESTROY: PostQuitMessage(0); break; default: return DefWindowProc(hWnd, message, wParam, lParam); break; } return 0; }  
```  
  
## Voir aussi  
 [Applications de bureau Windows](../windows/windows-desktop-applications-cpp.md)