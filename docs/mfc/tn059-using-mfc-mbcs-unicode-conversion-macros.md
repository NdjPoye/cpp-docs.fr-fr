---
title: "TN059&#160;: utilisation des macros de conversion MBCS/Unicode MFC | Microsoft Docs"
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
  - "vc.mfc.mbcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conversion (macros) (C++)"
  - "convertir (Unicode)"
  - "macros (C++), MBCS (macros de conversion)"
  - "MBCS (C++), macros de conversion"
  - "MFCANS32.DLL"
  - "TN059"
  - "Unicode (C++), macros de conversion"
  - "Unicode (C++), interfaces OLE"
ms.assetid: a2aab748-94d0-4e2f-8447-3bd07112a705
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN059&#160;: utilisation des macros de conversion MBCS/Unicode MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 Cette remarque décrit comment utiliser les macros de conversion de MBCS Ou Unicode, définies dans AFXPRIV.H.  Il est très utile si votre application gère directement les API OLE ou pour une raison quelconque, souvent les besoins de convertir les macros entre Unicode et MBCS.  
  
## Vue d'ensemble  
 Dans MFC 3.x, une DLL spéciale a été utilisé \(MFCANS32.DLL\) pour convertir automatiquement entre Unicode et MBCS lorsque des interfaces OLE étaient appelées.  Cette DLL est presque une couche transparente qui autorisait les applications OLE d'être écrit que si les API OLE et interfaces sont MBCS, même si elles figurent toujours de type Unicode \(sauf pour Macintosh\).  Si cette couche a des applications commodes et autorisées d'être transférées rapidement de Win16 sur Win32 \(MFC, Microsoft Word, Excel, et VBA, sont juste certaines applications Microsoft ayant utilisé cette technologie\), elle avait un gain de performance parfois significatif.  Pour cette raison, MFC 4.x n'utilise pas cette DLL et ne parle pas directement aux interfaces OLE Unicode.  Pour cela, les besoins de MFC conversion en Unicode vers MBCS lors d'un appel à une interface OLE, et souvent les besoins de la conversion vers MBCS Unicode pour l'implémentation d'une interface OLE.  Pour gérer cela facilement et efficacement, plusieurs macros ont été créées pour faciliter cette conversion.  
  
 Un des plus grands obstacles de créer un tel ensemble de macros est l'allocation de mémoire.  Les chaînes ne peuvent pas être converti en place, la nouvelle mémoire pour stocker les résultats convertis doit être allouée.  Cela peut avoir été appelée avec un code semblable à celui\-ci :  
  
```  
// we want to convert an MBCS string in lpszA  
int nLen = MultiByteToWideChar(CP_ACP, 0,lpszA, -1, NULL, NULL);  
LPWSTR lpszW = new WCHAR[nLen];  
MultiByteToWideChar(CP_ACP, 0,   
   lpszA, -1, lpszW, nLen);  
// use it to call OLE here  
pI->SomeFunctionThatNeedsUnicode(lpszW);  
// free the string  
delete[] lpszW;  
```  
  
 Cette méthode sous la forme d'un nombre de problèmes.  Le principal problème est qu'il y a beaucoup de code à écrire, tester, et déboguer.  Tout ce qui est un appel de fonction simple, est maintenant beaucoup plus complexe.  De plus, il existe une surcharge d'exécution significative ce faisant.  La mémoire doit être allouée sur le segment et être libérée chaque fois qu'une conversion est effectuée.  Enfin, le code ci\-dessus doit s'approprier `#ifdefs` pour les versions Unicode et de Macintosh \(qui ne nécessitent pas cette conversion pour avoir lieu\).  
  
 La solution que nous avons choisi est de créer des macros à 1\) masquer la différence entre les différentes plateformes, 2\) utiliser une méthode d'allocation de mémoire efficace, 3\) il est simple d'insérer dans le code source existant.  Voici un exemple de l'une des définitions :  
  
```  
#define A2W(lpa) (\  
    ((LPCSTR)lpa == NULL) ? NULL : (\  
          _convert = (strnlen(lpa)+1),\  
        AfxA2WHelper((LPWSTR) alloca(_convert*2),   
      lpa, _convert)\  
    )\  
)  
```  
  
 Utiliser cette macro au lieu du code ci\-dessus et les opérations sont beaucoup plus simple :  
  
```  
// use it to call OLE here  
USES_CONVERSION;  
pI->SomeFunctionThatNeedsUnicode(T2OLE(lpszA));  
```  
  
 Il existe des appels supplémentaires lorsque la conversion est nécessaire, mais l'utilisation de macros est simple et efficace.  
  
 L'implémentation de chaque macro utilise la fonction \_alloca\(\) pour allouer de la mémoire de la pile au lieu du segment.  Allouer de la mémoire de la pile est beaucoup plus rapide que l'allocation de la mémoire sur le segment, et la mémoire est automatiquement libérée lorsque la fonction est quittée.  En outre, les macros évitent d'appeler plusieurs fois **MultiByteToWideChar** \(ou **WideCharToMultiByte**\).  Cette opération s'effectue en allouant un peu plus de mémoire que nécessaire.  Nous savons qu'un MBC convertit dans au plus un **WCHAR** et que pour chaque **WCHAR** nous prendrons un maximum de deux octets du MBC.  En allouant un peu plus que nécessaire, mais toujours suffisamment pour gérer la conversion de l'appel du deuxième deuxième appel à la fonction de conversion est évité.  L'appel à la fonction d'assistance **AfxA2Whelper** réduit le nombre de transmissions de type push des arguments qui doivent être réalisés pour effectuer la conversion \(cela entraîne la plus petite code, que s'il **MultiByteToWideChar** appelé directement\).  
  
 Pour que les macros aient de l'espace pour store, il est nécessaire de déclarer une variable locale appelée le \_convert qui fait suivre dans une fonction qui utilise les macros de conversion.  Cela s'effectue en appelant la macro de **UTILISER\_CONVERSION** tel qu'il est vu précédemment dans l'exemple.  
  
 Il existe des macros génériques de conversion OLE et de macros spécifiques.  Ces deux différents ensembles de macros sont décrits ci\-dessous.  Toutes les macros résident dans AFXPRIV.H.  
  
## Macros de conversion génériques  
 Les macros génériques de conversion forment le mécanisme sous\-jacent.  L'exemple de macro et l'implémentation présentés dans la section précédente, A2W, est une telle macro « générique ».  Il n'est pas liée à OLE en particulier.  L'ensemble de macros génériques est indiquée ci\-dessous :  
  
```  
A2CW      (LPCSTR) -> (LPCWSTR)  
A2W      (LPCSTR) -> (LPWSTR)  
W2CA      (LPCWSTR) -> (LPCSTR)  
W2A      (LPCWSTR) -> (LPSTR)  
```  
  
 En plus de rendre les conversions de texte, il existe également des macros et des fonctions d'assistance pour convertir `TEXTMETRIC`, `DEVMODE`, `BSTR`, et les chaînes allouées par OLE.  Ces macros\-instructions ne sont pas traitée dans cette discussion – reportez\-vous à AFXPRIV.H pour plus d'informations sur ces macros\-instructions.  
  
## OLE Conversion de macros  
 Les conversions de macros OLE sont conçues spécifiquement pour gérer les fonctions qui attendent des caractères de **OLESTR**.  Si vous examinez les en\-têtes OLE, vous verrez plusieurs références à **LPCOLESTR** et **OLECHAR**.  Ces types sont utilisés pour faire référence au type de caractères utilisés dans les interfaces OLE d'une manière qui n'est pas spécifique à la plateforme.  Mappé à**OLECHAR** à `char` dans Win16 et les plateformes Macintosh et **WCHAR** de Win32.  
  
 Pour conserver le nombre de directives de **\#ifdef** dans le code de MFC au minimum nous avons une macro similaire pour chaque conversion où les chaînes OLE sont impliquées.  Les macros suivantes sont le plus souvent utilisés :  
  
```  
T2COLE   (LPCTSTR) -> (LPCOLESTR)  
T2OLE   (LPCTSTR) -> (LPOLESTR)  
OLE2CT   (LPCOLESTR) -> (LPCTSTR)  
OLE2T   (LPCOLESTR) -> (LPCSTR)  
```  
  
 De nouveau, il existe des macros similaires pour effectuer `TEXTMETRIC`, `DEVMODE`, `BSTR`, et les chaînes allouées par OLE.  Pour plus d'informations, consultez AFXPRIV.H.  
  
## Autres considérations  
 N'utilisez pas les macros dans une boucle étroite.  Par exemple, vous ne souhaitez pas écrire le type de code suivant :  
  
```  
void BadIterateCode(LPCTSTR lpsz)  
{  
   USES_CONVERSION;  
   for (int ii = 0; ii < 10000; ii++)  
      pI->SomeMethod(ii, T2COLE(lpsz));  
}  
```  
  
 Le code ci\-dessus peut résulter lors de l'allocation de mégaoctets de la mémoire sur la pile selon ce qu'est le contenu de la chaîne `lpsz` \!  Il prend également le temps de convertir la chaîne de chaque itération de la boucle.  À la place, déplacez de telles conversions constantes en dehors de la boucle :  
  
```  
void MuchBetterIterateCode(LPCTSTR lpsz)  
{  
   USES_CONVERSION;  
   LPCOLESTR lpszT = T2COLE(lpsz);  
   for (int ii = 0; ii < 10000; ii++)  
      pI->SomeMethod(ii, lpszT);  
}  
```  
  
 Si la chaîne n'est pas constante, encapsulez l'appel de la méthode à une fonction.  Cela permet la mémoire tampon de la conversion à chaque fois.  Par exemple :  
  
```  
void CallSomeMethod(int ii, LPCTSTR lpsz)  
{  
   USES_CONVERSION;  
   pI->SomeMethod(ii, T2COLE(lpsz));  
}  
  
void MuchBetterIterateCode2(LPCTSTR* lpszArray)  
{  
   for (int ii = 0; ii < 10000; ii++)  
      CallSomeMethod(ii, lpszArray[ii]);  
}  
```  
  
 Ne retourne jamais le résultat de l'une des macros, à moins que la valeur de retour est nécessaire pour faire une copie des données avant le retour.  Par exemple, ce code est mauvais :  
  
```  
LPTSTR BadConvert(ISomeInterface* pI)  
{  
   USES_CONVERSION;  
   LPOLESTR lpsz = NULL;  
   pI->GetFileName(&lpsz);  
   LPTSTR lpszT = OLE2T(lpsz);  
   CoMemFree(lpsz);  
   return lpszT; // bad! returning alloca memory  
}  
```  
  
 Le code ci\-dessus peut être résolu en modifiant la valeur de retour à quelque chose qui copie la valeur :  
  
```  
CString BetterConvert(ISomeInterface* pI)  
{  
   USES_CONVERSION;  
   LPOLESTR lpsz = NULL;  
   pI->GetFileName(&lpsz);  
   LPTSTR lpszT = OLE2T(lpsz);  
   CoMemFree(lpsz);  
   return lpszT; // CString makes copy  
}  
```  
  
 Les macros sont faciles à utiliser et faciles à insérer dans votre code, mais comme vous pouvez déterminer les oppositions ci\-dessus, vous devez prendre soin de leur utilisation.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)