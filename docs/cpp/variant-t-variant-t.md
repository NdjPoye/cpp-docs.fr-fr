---
title: "_variant_t::_variant_t | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t::_variant_t"
  - "_variant_t._variant_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_variant_t (classe), constructeur"
  - "_variant_t (méthode)"
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _variant_t::_variant_t
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Construit un objet `_variant_t`.  
  
## Syntaxe  
  
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
  
#### Paramètres  
 *varSrc*  
 Objet **VARIANT** à copier dans le nouvel objet `_variant_t`.  
  
 *pVarSrc*  
 Pointeur vers un objet **VARIANT** à copier dans le nouvel objet `_variant_t`.  
  
 *var\_t\_Src*  
 Objet `_variant_t` à copier dans le nouvel objet `_variant_t`.  
  
 `fCopy`  
 Si la valeur est false, l'objet **VARIANT** fourni est attaché au nouvel objet `_variant_t` sans effectuer de nouvelle copie via **VariantCopy**.  
  
 *ISrc, sSrc*  
 Valeur entière à copier dans le nouvel objet `_variant_t`.  
  
 `vtSrc`  
 Valeur **VARTYPE** du nouvel objet `_variant_t`.  
  
 *fltSrc, dblSrc*  
 Valeur numérique à copier dans le nouvel objet `_variant_t`.  
  
 `cySrc`  
 Objet **CY** à copier dans le nouvel objet `_variant_t`.  
  
 `bstrSrc`  
 Objet `_bstr_t` à copier dans le nouvel objet `_variant_t`.  
  
 *strSrc, wstrSrc*  
 Chaîne à copier dans le nouvel objet `_variant_t`.  
  
 `bSrc`  
 Valeur `bool` à copier dans le nouvel objet `_variant_t`.  
  
 `pIUknownSrc`  
 Pointeur d'interface COM vers un objet **VT\_UNKNOWN** à encapsuler dans le nouvel objet `_variant_t`.  
  
 `pDispSrc`  
 Pointeur d'interface COM vers un objet **VT\_DISPATCH** à encapsuler dans le nouvel objet `_variant_t`.  
  
 `decSrc`  
 Valeur **DECIMAL** à copier dans le nouvel objet `_variant_t`.  
  
 `bSrc`  
 Valeur **BYTE** à copier dans le nouvel objet `_variant_t`.  
  
 `cSrc`  
 Valeur `char` à copier dans le nouvel objet `_variant_t`.  
  
 *usSrc*  
 Valeur **unsigned short** à copier dans le nouvel objet `_variant_t`.  
  
 *ulSrc*  
 Valeur `unsigned long` à copier dans le nouvel objet `_variant_t`.  
  
 `iSrc`  
 Valeur `int` à copier dans le nouvel objet `_variant_t`.  
  
 *uiSrc*  
 Valeur `unsigned int` à copier dans le nouvel objet `_variant_t`.  
  
 *i8Src*  
 Valeur \_\_**int64** à copier dans le nouvel objet `_variant_t`.  
  
 *ui8Src*  
 Valeur **unsigned \_\_int64** à copier dans le nouvel objet `_variant_t`.  
  
## Notes  
  
-   **\_variant\_t\( \)** Construit un objet `_variant_t` vide, `VT_EMPTY`.  
  
-   **\_variant\_t\( VARIANT&**  *varSrc*  **\)** Construit un objet `_variant_t` à partir d'une copie de l'objet **VARIANT**.  Le type variant est conservé.  
  
-   **\_variant\_t\( VARIANT\***  *pVarSrc*  **\)** Construit un objet `_variant_t` à partir d'une copie de l'objet **VARIANT**.  Le type variant est conservé.  
  
-   **\_variant\_t\( \_variant\_t&**  *var\_t\_Src*  **\)** Construit un objet `_variant_t` à partir d'un autre objet `_variant_t`.  Le type variant est conservé.  
  
-   **\_variant\_t\( VARIANT&**  *varSrc* **, bool**  `fCopy`  **\)** Construit un objet `_variant_t` à partir d'un objet **VARIANT** existant.  Si `fCopy` a la valeur **false**, l'objet **VARIANT** est lié au nouvel objet sans créer de copie.  
  
-   **\_variant\_t\( short**  *sSrc* **, VARTYPE**  `vtSrc`  **\= VT\_I2 \)** Construit un objet `_variant_t` de type `VT_I2` ou `VT_BOOL` à partir d'une valeur entière **short**.  Toute autre valeur **VARTYPE** génère une erreur dans `E_INVALIDARG`.  
  
-   **\_variant\_t\( long**  `lSrc` **, VARTYPE**  `vtSrc`  **\= VT\_I4 \)** Construit un objet `_variant_t` de type `VT_I4`, `VT_BOOL` ou `VT_ERROR` à partir d'une valeur entière **long**.  Toute autre valeur **VARTYPE** génère une erreur dans `E_INVALIDARG`.  
  
-   **\_variant\_t\( float**  `fltSrc`  **\)** Construit un objet `_variant_t` de type `VT_R4` à partir d'une valeur numérique **float**.  
  
-   **\_variant\_t\( double**  `dblSrc` **, VARTYPE**  `vtSrc`  **\= VT\_R8 \)** Construit un objet `_variant_t` de type `VT_R8` ou `VT_DATE` à partir d'une valeur numérique **double**.  Toute autre valeur **VARTYPE** génère une erreur dans `E_INVALIDARG`.  
  
-   **\_variant\_t\( CY&**  `cySrc`  **\)** Construit un objet `_variant_t` de type `VT_CY` à partir d'un objet **CY**.  
  
-   **\_variant\_t\( \_bstr\_t&**  `bstrSrc`  **\)** Construit un objet `_variant_t` de type `VT_BSTR` à partir d'un objet `_bstr_t`.  Un nouvel objet `BSTR` est alloué.  
  
-   **\_variant\_t\( wchar\_t \*** *wstrSrc*  **\)** Construit un objet `_variant_t` de type `VT_BSTR` à partir d'une chaîne Unicode.  Un nouvel objet `BSTR` est alloué.  
  
-   **\_variant\_t\( char\***  `strSrc`  **\)** Construit un objet `_variant_t` de type `VT_BSTR` à partir d'une chaîne.  Un nouvel objet `BSTR` est alloué.  
  
-   **\_variant\_t\( bool**  `bSrc`  **\)** Construit un objet `_variant_t` de type `VT_BOOL` à partir d'une valeur `bool`.  
  
-   **\_variant\_t\( IUnknown\***  `pIUknownSrc` **, bool**  `fAddRef`  **\= true \)** Construit un objet `_variant_t` de type **VT\_UNKNOWN** à partir d'un pointeur d'interface COM.  Si `fAddRef` a la valeur **true**, `AddRef` est appelé sur le pointeur d'interface fourni pour faire correspondre l'appel à **Release** qui se produira lors de la destruction de l'objet `_variant_t`.  Il vous appartient d'appeler **Release** sur le pointeur d'interface fourni.  Si `fAddRef` a la valeur **false**, ce constructeur prend la propriété du pointeur d'interface fourni ; n'appelez pas **Release** sur le pointeur d'interface fourni.  
  
-   **\_variant\_t\( IDispatch\***  `pDispSrc` **, bool**  `fAddRef`  **\= true \)** Construit un objet `_variant_t` de type **VT\_DISPATCH** à partir d'un pointeur d'interface COM.  Si `fAddRef` a la valeur **true**, `AddRef` est appelé sur le pointeur d'interface fourni pour faire correspondre l'appel à **Release** qui se produira lors de la destruction de l'objet `_variant_t`.  Il vous appartient d'appeler **Release** sur le pointeur d'interface fourni.  Si **fAddRef** a la valeur false, ce constructeur prend la propriété du pointeur d'interface fourni ; n'appelez pas **Release** sur le pointeur d'interface fourni.  
  
-   **\_variant\_t\( DECIMAL&**  `decSrc`  **\)** Construit un objet `_variant_t` de type **VT\_DECIMAL** à partir d'une valeur **DECIMAL**.  
  
-   **\_variant\_t\( BYTE**  `bSrc`  **\)** Construit un objet `_variant_t` de type `VT_UI1` à partir d'une valeur **BYTE**.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_variant\_t \(classe\)](../cpp/variant-t-class.md)