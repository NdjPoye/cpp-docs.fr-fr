---
title: "TN001&#160;: inscription de classe Windows | Microsoft Docs"
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
  - "vc.registration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxRegisterClass (fonction)"
  - "TN001"
  - "WNDCLASS"
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
caps.latest.revision: 16
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN001&#160;: inscription de classe Windows
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette remarque décrit les routines MFC qui signalent les [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)es spéciales requises par Microsoft Windows.  Les attributs spécifiques à `WNDCLASS` utilisés par MFC et Windows sont présentés.  
  
## Le problème  
 Les attributs [CWnd](../mfc/reference/cwnd-class.md) objet, comme un handle `HWND` dans Windows, sont stockées dans deux emplacements : l'objet window et `WNDCLASS`.  Le nom `WNDCLASS` est transmis aux fonctions générales de conception de fenêtre comme [CWnd::Create](../Topic/CWnd::Create.md) et [CFrameWnd::Create](../Topic/CFrameWnd::Create.md) dans le paramètre `lpszClassName`.  
  
 Cet `WNDCLASS` doit être stocké par l'une des ces quatres méthodes :  
  
-   Implicitement à l'aide d'une `WNDCLASS` fournie par MFC.  
  
-   Implicitement en sous\-classant un contrôle Windows \(ou un autre contrôle\).  
  
-   De manière explicite en appelant les [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) ou [AfxRegisterClass](../Topic/AfxRegisterClass.md) MFC.  
  
-   De manière explicite en appelant la routine [RegisterClass](http://msdn.microsoft.com/library/windows/desktop/ms633586) Windows.  
  
## Champs WNDCLASS  
 La structure `WNDCLASS` comprend des champs individuels qui décrivent une classe de fenêtre.  Le tableau suivant affiche les champs et indique comment ils sont utilisés dans une application MFC :  
  
|Champ|Description|  
|-----------|-----------------|  
|`lpfnWndProc`|window proc, doit être un `AfxWndProc`|  
|`cbClsExtra`|inutilisé \(devrait être nul\)|  
|`cbWndExtra`|inutilisé \(devrait être nul\)|  
|`hInstance`|automatiquement rempli avec [AfxGetInstanceHandle](../Topic/AfxGetInstanceHandle.md)|  
|`hIcon`|l'icône de windows frames, consultez ci\-dessous|  
|`hCursor`|le curseur lorsque la souris sur fenêtre, consultez ci\-dessous|  
|`hbrBackground`|couleur d'arrière\-plan, consultez ci\-dessous|  
|`lpszMenuName`|inutilisé \(devrait être NULL\)|  
|`lpszClassName`|nom de classe, consultez ci\-dessous|  
  
## WNDCLASSes fournies  
 Les versions antérieures de MFC \(avant MFC 4.0\), fournissaient plusieurs classes Windows prédéfinies.  Ces classes Windows ne sont plus disponibles par défaut.  Les applications doivent utiliser `AfxRegisterWndClass` avec les paramètres appropriés.  
  
 Si l'application fournit à une ressource l'ID de ressource spécifié \(par exemple, AFX\_IDI\_STD\_FRAME\), MFC utilise cette ressource.  Sinon elle utilisera la ressource par défaut.  Pour l'icône, l'icône d'application standard est utilisée, et pour le curseur, le curseur standard de flèche est utilisé.  
  
 Deux icônes prennent en charge les applications MDI avec des types de document unique : une icône pour l'application principale, l'autre icône pour les fenêtres de document iconique\/MDIChild.  Pour plusieurs types de document avec des icônes, vous devez stocker des supplémentaires `WNDCLASS` ou utiliser la fonction [CFrameWnd::LoadFrame](../Topic/CFrameWnd::LoadFrame.md).  
  
 `CFrameWnd::LoadFrame` stocke `WNDCLASS` en utilisant l'ID de l'icône que vous spécifiez comme le premier paramètre et les attributs standards suivants :  
  
-   style de la classe : CS\_DBLCLKS &#124; CS\_HREDRAW &#124; CS\_VREDRAW ;  
  
-   icône AFX\_IDI\_STD\_FRAME  
  
-   Curseur Flèche  
  
-   Couleur d'arrière\-plan COLOR\_WINDOW  
  
 Les valeurs de la couleur d'arrière\-plan et le curseur pour [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) ne sont pas utilisés car la zone client `CMDIFrameWnd` est complètement couverte par la fenêtre **MDICLIENT**.  Microsoft n'encourage pas le sous\-classement la fenêtre **MDICLIENT** donc utilisez des couleurs et les types de curseurs standard si possible.  
  
## Contrôles de sous\-classement et sur\-classement  
 Si vous sous\-classez ou sur\-classez un contrôle Windows \(par exemple, [CButton](../mfc/reference/cbutton-class.md)\) alors votre classe obtient automatiquement les attributs `WNDCLASS` fournis dans l'implémentation windows de ce contrôle.  
  
## La fonction AfxRegisterWndClass  
 MFC fournit une fonction d'assistance pour stocker une classe de fenêtre.  Étant donnée une collection d'attributs \(style, curseur, pinceau d'arrière\-plan, et icône de classe de fenêtre\), un nom synthétique est généré, et la classe de fenêtre résultante est stockée.  Par exemple :  
  
```  
const char* AfxRegisterWndClass(UINT nClassStyle, HCURSOR hCursor, HBRUSH hbrBackground, HICON hIcon);  
```  
  
 Cette fonction retourne une chaîne temporaire du nom de classe de fenêtre stocké généré.  Pour plus d'informations sur la fonction xonsultez [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md).  
  
 La chaîne retournée est un pointeur temporaire vers une mémoire tampon de chaîne statique.  Il est valide jusqu'à l'appel suivant à `AfxRegisterWndClass`.  Si vous souhaitez conserver cette chaîne, enregistrez\-la dans une variable [CString](../atl-mfc-shared/using-cstring.md), comme dans l'exemple suivant :  
  
```  
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);  
...  
CWnd* pWnd = new CWnd;  
pWnd->Create(strWndClass, ...);  
...  
```  
  
 `AfxRegisterWndClass` lève une [CResourceException](../mfc/reference/cresourceexception-class.md) si la classe de fenêtre a échoué son enregistrement \(en raison de paramètres incorrect, ou de mémoire Windows pleine\).  
  
## Les fonctions RegisterClass et AfxRegisterClass  
 Si vous souhaitez faire quelque chose plus complexe que ce que `AfxRegisterWndClass` permet, appelez l'API Windows `RegisterClass` ou la fonction `AfxRegisterClass`de MFC.  `CWnd`, [CFrameWnd](../mfc/reference/cframewnd-class.md) et les fonctions [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)`Create` prennent un nom de chaîne `lpszClassName` pour la classe de fenêtre comme premier paramètre.  Vous pouvez utiliser tout nom de classe de fenêtre stocké, quelle que soit la méthode graâce à laquelle vous l'avez enregistré.  
  
 Il est important d'utiliser `AfxRegisterClass` \(ou `AfxRegisterWndClass`\) dans une DLL sur Win32.  Win32 n'annule pas automatiquement l'inscription les classes stockées par une DLL, vous devez explicitement annuler l'inscription des classes lorsque la DLL est terminée.  En utilisant `AfxRegisterClass` au lieu de `RegisterClass` ceci est géré automatiquement.  `AfxRegisterClass` conserve une liste des classes enregistrées par la DLL et annule leur inscription automatiquement lorsque la DLL se termine.  Lorsque vous utilisez `RegisterClass` dans une DLL, vous devez vous assurer que toutes les classes ont désinscrites lorsque la DLL est terminée \(dans votre fonction [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583) \).  Dans le cas contraire, cela peut entraîner un échec inattendu de `RegisterClass` lorsque une autre application cliente tente d'utiliser la DLL.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)