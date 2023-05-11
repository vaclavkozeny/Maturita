# Frameworky MVC

`MVC, MVP, MVVM, Model, View, Controller, Presenter, Page, PageModel, request, response, http`

## MVC

- `Model – View – Controller`
- architektura pro vývoj aplikací
- vznikla pro zanesení řádu do vývoje aplikací
- základem je **model**, **view** a **controller**
- je základem pro další architektury

### Controler

- řídící jednotka celé architektury
- drží celou aplikaci pohromadě
- od uživatele dostává dotazy na data
- propojuje view a model
- volá metody
- získaná data dále předávána view

## View

- zobrazuej data uživateli

## Model

- struktura dat
- funkcionalita aplikace
- návrh DB

## MVP

- conroller nahrazen presenterem
- snaha od sebe oddělit jednotlivé vrstvy
- presenter řídí veškerou komunikaci a reaguje na změny dat

<image src="./images/mvp.png">

## MVVM

- presenter je nahrazen viewmodelem
- zatím vrcholná architektura
- viewmodel s view komunikuje pomocí data bindingu, vnitřní logika aplikace
- model se stará o data a stav aplikace

<image src="./images/mvvm.png">

## PageModel

- ASP.NET Razor pages

### Page

- view

### PageModel

- spojení controlleru a modelu
- stará se o data, stav aplikace a komunikuje s view

## HTTP

- přenos 'dat' webových aplikací
- **request**
  - požadavek
  - žádám API o data
- **responce**
  - odpověď
  - 'dostávám' data zpět
  - API vrací data

<image src="./images/http.png">
