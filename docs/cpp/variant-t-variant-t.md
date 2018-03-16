---
title: _variant_t::_variant_t | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::_variant_t
dev_langs:
- C++
helpviewer_keywords:
- _variant_t class [C++], constructor
- _variant_t method [C++]
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cd85a54e9f73352894f6575051fe1ea8be0698fb
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="varianttvariantt"></a>_variant_t::_variant_t
**Section spécifique à Microsoft**  
  
 Construit un objet `_variant_t`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      _variant_t( ) throw( );  
  
_variant_t(  
   const VARIANT& varSrc   
);  
  
_variant_t(  
   const VARIANT* pVarSrc   
);  
  
_variant_t(  
   const _variant_t& var_t_Src   
);  
  
_variant_t(  
   VARIANT& varSrc,  
   bool fCopy   
);  
  
_variant_t(  
   short sSrc,  
   VARTYPE vtSrc = VT_I2   
);  
  
_variant_t(  
   long lSrc,  
   VARTYPE vtSrc = VT_I4   
);  
  
_variant_t(  
   float fltSrc   
) throw( );  
  
_variant_t(  
   double dblSrc,  
   VARTYPE vtSrc = VT_R8   
);  
  
_variant_t(  
   const CY& cySrc   
) throw( );  
  
_variant_t(  
   const _bstr_t& bstrSrc   
);  
  
_variant_t(  
   const wchar_t *wstrSrc   
);  
  
_variant_t(  
   const char* strSrc   
);  
  
_variant_t(  
   IDispatch* pDispSrc,  
   bool fAddRef = true   
) throw( );  
  
_variant_t(  
   bool bSrc   
) throw( );  
  
_variant_t(  
   IUnknown* pIUknownSrc,  
   bool fAddRef = true   
) throw( );  
  
_variant_t(  
   const DECIMAL& decSrc   
) throw( );  
  
_variant_t(  
   BYTE bSrc   
) throw( );  
  
variant_t(  
   char cSrc  
) throw();  
  
_variant_t(  
   unsigned short usSrc  
) throw();  
  
_variant_t(  
   unsigned long ulSrc  
) throw();  
  
_variant_t(  
   int iSrc  
) throw();  
  
_variant_t(  
   unsigned int uiSrc  
) throw();  
  
_variant_t(  
   __int64 i8Src  
) throw();  
  
_variant_t(  
   unsigned __int64 ui8Src  
) throw();  
```  
  
#### <a name="parameters"></a>Paramètres  
 *varSrc*  
 A **VARIANT** à copier dans le nouvel objet `_variant_t` objet.  
  
 *pVarSrc*  
 Pointeur vers un **VARIANT** à copier dans le nouvel objet `_variant_t` objet.  
  
 *var_t_Src*  
 Objet `_variant_t` à copier dans le nouvel objet `_variant_t`.  
  
 `fCopy`  
 Si la valeur est false, fourni **VARIANT** objet est attaché au nouvel `_variant_t` objet sans effectuer de nouvelle copie par **VariantCopy**.  
  
 *ISrc, sSrc*  
 Valeur entière à copier dans le nouvel objet `_variant_t`.  
  
 `vtSrc`  
 Le **VARTYPE** pour le nouveau `_variant_t` objet.  
  
 *fltSrc, dblSrc*  
 Valeur numérique à copier dans le nouvel objet `_variant_t`.  
  
 `cySrc`  
 A **CY** à copier dans le nouvel objet `_variant_t` objet.  
  
 `bstrSrc`  
 Objet `_bstr_t` à copier dans le nouvel objet `_variant_t`.  
  
 *strSrc, wstrSrc*  
 Chaîne à copier dans le nouvel objet `_variant_t`.  
  
 `bSrc`  
 Valeur `bool` à copier dans le nouvel objet `_variant_t`.  
  
 `pIUknownSrc`  
 Pointeur d’interface COM vers un **VT_UNKNOWN** à encapsuler dans le nouvel objet `_variant_t` objet.  
  
 `pDispSrc`  
 Pointeur d’interface COM vers un **VT_DISPATCH** à encapsuler dans le nouvel objet `_variant_t` objet.  
  
 `decSrc`  
 A **décimal** valeur à copier dans le nouvel `_variant_t` objet.  
  
 `bSrc`  
 A **octets** valeur à copier dans le nouvel `_variant_t` objet.  
  
 `cSrc`  
 Valeur `char` à copier dans le nouvel objet `_variant_t`.  
  
 *usSrc*  
 A **court non signé** valeur à copier dans le nouvel `_variant_t` objet.  
  
 *ulSrc*  
 Valeur `unsigned long` à copier dans le nouvel objet `_variant_t`.  
  
 `iSrc`  
 Valeur `int` à copier dans le nouvel objet `_variant_t`.  
  
 *uiSrc*  
 Valeur `unsigned int` à copier dans le nouvel objet `_variant_t`.  
  
 *i8Src*  
 Un __**int64** valeur à copier dans le nouvel `_variant_t` objet.  
  
 *ui8Src*  
 Un **unsigned __int64** valeur à copier dans le nouvel `_variant_t` objet.  
  
## <a name="remarks"></a>Notes  
  
-   **_variant_t ()** construit vide `_variant_t` objet, `VT_EMPTY`.  
  
-   **_variant_t (VARIANT &***varSrc***)** construit un `_variant_t` objet à partir d’une copie de la **VARIANT** objet.     Le type variant est conservé.  
  
-   **_variant_t (VARIANT\****pVarSrc***)** construit un `_variant_t` objet à partir d’une copie de la **VARIANT** objet.     Le type variant est conservé.  
  
-   **_variant_t (classe _variant_t &***var_t_Src***)** construit un `_variant_t` objet à partir d’un autre `_variant_t` objet.     Le type variant est conservé.  
  
-   **_variant_t (VARIANT &***varSrc* **, bool**`fCopy`**)** construit un `_variant_t` objet d’un existant  **VARIANT** objet.       Si `fCopy` est **false**, le **VARIANT** objet est attaché au nouvel objet sans faire de copie.  
  
-   **_variant_t (court***sSrc* **, VARTYPE**`vtSrc`**= VT_I2)** construit un `_variant_t` objet de type `VT_I2` ou `VT_BOOL` d’un **court** valeur entière.       N’importe quel autre **VARTYPE** entraîne une `E_INVALIDARG` erreur.  
  
-   **_variant_t (long** `lSrc` **, VARTYPE**`vtSrc`**= VT_I4)** construit un `_variant_t` objet de type `VT_I4`, `VT_BOOL`, ou `VT_ERROR`d’un **long** valeur entière.       N’importe quel autre **VARTYPE** entraîne une `E_INVALIDARG` erreur.  
  
-   **_variant_t (float**`fltSrc`**)** construit un `_variant_t` objet de type `VT_R4` d’un **float** valeur numérique.      
  
-   **_variant_t (double** `dblSrc` **, VARTYPE**`vtSrc`**= VT_R8)** construit un `_variant_t` objet de type `VT_R8` ou `VT_DATE` à partir d’un **double** valeur numérique.       N’importe quel autre **VARTYPE** entraîne une `E_INVALIDARG` erreur.  
  
-   **_variant_t (CY &**`cySrc`**)** construit un `_variant_t` objet de type `VT_CY` d’un **CY** objet.      
  
-   **_variant_t (_bstr_t &**`bstrSrc`**)** construit un `_variant_t` objet de type `VT_BSTR` d’un `_bstr_t` objet.     Un nouvel objet `BSTR` est alloué.  
  
-   **_variant_t (wchar_t \***  *wstrSrc***)** construit un `_variant_t` objet de type `VT_BSTR` à partir d’une chaîne Unicode.   Un nouvel objet `BSTR` est alloué.  
  
-   **_variant_t (char\***`strSrc`**)** construit un `_variant_t` objet de type `VT_BSTR` à partir d’une chaîne.     Un nouvel objet `BSTR` est alloué.  
  
-   **_variant_t (bool**`bSrc`**)** construit un `_variant_t` objet de type `VT_BOOL` d’un `bool` valeur.      
  
-   **_variant_t (IUnknown\***  `pIUknownSrc` **, bool**`fAddRef`**= true)** construit un `_variant_t` objet de type **VT_UNKNOWN** à partir d’un pointeur d’interface COM.       Si `fAddRef` est **true**, puis `AddRef` est appelée sur le pointeur d’interface fourni pour faire correspondre l’appel à **version** qui se produit lorsque le `_variant_t` objet est détruit. Il vous incombe d’appeler **version** sur le pointeur d’interface fourni. Si `fAddRef` est **false**, ce constructeur prend possession du pointeur d’interface fourni ; n’appelez pas **version** sur le pointeur d’interface fourni.  
  
-   **_variant_t (IDispatch\***  `pDispSrc` **, bool**`fAddRef`**= true)** construit un `_variant_t` objet de type **VT_DISPATCH** à partir d’un pointeur d’interface COM.       Si `fAddRef` est **true**, puis `AddRef` est appelée sur le pointeur d’interface fourni pour faire correspondre l’appel à **version** qui se produit lorsque le `_variant_t` objet est détruit. Il vous incombe d’appeler **version** sur le pointeur d’interface fourni. Si **fAddRef** est false, ce constructeur prend possession du pointeur d’interface fourni ; n’appelez pas **version** sur le pointeur d’interface fourni.  
  
-   **_variant_t (décimal &**`decSrc`**)** construit un `_variant_t` objet de type **VT_DECIMAL** d’un **décimal** valeur.      
  
-   **_variant_t (octets**`bSrc`**)** construit un `_variant_t` objet de type `VT_UI1` d’un **octets** valeur.      
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [_variant_t, classe](../cpp/variant-t-class.md)