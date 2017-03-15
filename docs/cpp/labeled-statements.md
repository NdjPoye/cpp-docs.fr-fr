---
title: "Instructions &#233;tiquet&#233;es | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "goto"
  - "case"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "labeled (instruction)"
  - "instructions, labeled"
ms.assetid: 456a26d5-0fcc-4d1a-b71f-fa9ff3d73b91
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Instructions &#233;tiquet&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les étiquettes sont utilisées pour transférer le contrôle du programme directement à l'instruction spécifiée.  
  
```  
identifier :  statement  
case constant-expression :  statement  
default :  statement  
```  
  
 La portée d'une étiquette est la fonction entière dans laquelle elle est déclarée.  
  
## Notes  
 Il existe trois types d'instructions étiquetées.  Tous utilisent un deux\-points pour séparer un certain type d'étiquette de l'instruction.  Le cas et les étiquettes par défaut sont propres aux instructions case.  
  
```cpp  
#include <iostream>   
using namespace std;   
  
void test_label(int x) {  
  
    if (x == 1){  
        goto label1;  
    }  
    goto label2;  
  
label1:  
    cout << "in label1" << endl;  
    return;  
  
label2:  
    cout << "in label2" << endl;  
    return;  
}  
  
int main() {  
    test_label(1);  // in label1   
    test_label(2);  // in label2  
}  
  
```  
  
 **Instruction goto**  
  
 L'apparence d'une étiquette *identifier* dans le programme source déclare une étiquette.  Seule une instruction [goto](../cpp/goto-statement-cpp.md) peut transférer le contrôle vers une étiquette *identifier*.  Le fragment de code suivant illustre l'utilisation de l'instruction `goto`, ainsi qu'une étiquette *identifier* :  
  
 Une étiquette ne peut pas apparaître seule, mais doit toujours être attachée à une instruction.  Si une étiquette doit apparaître seule, placez une instruction null après l'étiquette.  
  
 L'étiquette a une portée de fonction et ne peut pas être redéclarée dans la fonction.  Toutefois, le même nom peut être utilisé en tant qu'étiquette dans différentes fonctions.  
  
```  
// labels_with_goto.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   using namespace std;  
   goto Test2;  
  
   cout << "testing" << endl;  
  
   Test2:  
      cerr << "At Test2 label." << endl;  
}  
  
//Output: At Test2 label.  
```  
  
 **Instruction case**  
  
 Les étiquettes qui apparaissent après le mot clé **case** ne peuvent pas apparaître à l'extérieur d'une instruction `switch`.  \(Cette restriction s'applique également au mot clé **default**.\) Le fragment de code suivant illustre l'utilisation correcte des étiquettes **case** :  
  
```  
// Sample Microsoft Windows message processing loop.  
switch( msg )  
{  
   case WM_TIMER:    // Process timer event.  
      SetClassWord( hWnd, GCW_HICON, ahIcon[nIcon++] );  
      ShowWindow( hWnd, SW_SHOWNA );  
      nIcon %= 14;  
      Yield();  
      break;  
  
   case WM_PAINT:  
      memset( &ps, 0x00, sizeof(PAINTSTRUCT) );  
      hDC = BeginPaint( hWnd, &ps );   
      EndPaint( hWnd, &ps );  
      break;  
  
   default:  
      // This choice is taken for all messages not specifically  
      //  covered by a case statement.  
  
      return DefWindowProc( hWnd, Message, wParam, lParam );  
      break;  
}  
```  
  
## Étiquettes dans l'instruction case  
 Les étiquettes qui apparaissent après le mot clé **case** ne peuvent pas apparaître à l'extérieur d'une instruction `switch`.  \(Cette restriction s'applique également au mot clé **default**.\) Le fragment de code suivant illustre l'utilisation correcte des étiquettes **case** :  
  
```  
// Sample Microsoft Windows message processing loop.  
switch( msg )  
{  
   case WM_TIMER:    // Process timer event.  
      SetClassWord( hWnd, GCW_HICON, ahIcon[nIcon++] );  
      ShowWindow( hWnd, SW_SHOWNA );  
      nIcon %= 14;  
      Yield();  
      break;  
  
   case WM_PAINT:  
      // Obtain a handle to the device context.  
      // BeginPaint will send WM_ERASEBKGND if appropriate.  
  
      memset( &ps, 0x00, sizeof(PAINTSTRUCT) );  
      hDC = BeginPaint( hWnd, &ps );  
  
      // Inform Windows that painting is complete.  
  
      EndPaint( hWnd, &ps );  
      break;  
  
   case WM_CLOSE:  
      // Close this window and all child windows.  
  
      KillTimer( hWnd, TIMER1 );  
      DestroyWindow( hWnd );  
      if ( hWnd == hWndMain )  
         PostQuitMessage( 0 );  // Quit the application.  
      break;  
  
   default:  
      // This choice is taken for all messages not specifically  
      //  covered by a case statement.  
  
      return DefWindowProc( hWnd, Message, wParam, lParam );  
      break;  
}  
```  
  
## Étiquettes dans l'instruction goto  
 L'apparence d'une étiquette *identifier* dans le programme source déclare une étiquette.  Seule une instruction [goto](../cpp/goto-statement-cpp.md) peut transférer le contrôle vers une étiquette *identifier*.  Le fragment de code suivant illustre l'utilisation de l'instruction `goto` ainsi que d'une étiquette *identifier* :  
  
 Une étiquette ne peut pas apparaître seule, mais doit toujours être attachée à une instruction.  Si une étiquette doit apparaître seule, placez une instruction null après l'étiquette.  
  
 L'étiquette a une portée de fonction et ne peut pas être redéclarée dans la fonction.  Toutefois, le même nom peut être utilisé en tant qu'étiquette dans différentes fonctions.  
  
```  
// labels_with_goto.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   using namespace std;  
   goto Test2;  
  
   cout << "testing" << endl;  
  
   Test2:  
      cerr << "At Test2 label." << endl;  
// At Test2 label.  
}  
  
```  
  
## Voir aussi  
 [Vue d'ensemble des instructions C\+\+](../cpp/overview-of-cpp-statements.md)   
 [switch, instruction \(C\+\+\)](../cpp/switch-statement-cpp.md)