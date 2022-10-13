INSTALAR PAQUETE
composer require psr/simple-cache:^2 maatwebsite/excel

PUBLICAR LIBRERIA 
php artisan vendor:publish --provider="Maatwebsite\Excel\ExcelServiceProvider" --tag=config

CREAR ARCHIVO PARA EXPORTAR
php artisan make:export UsersExport --model=User

CREAR RUTAS GET

CREAR VISTAS 
Visual


INVOCAR A LA LIBRERIA AL CONTROLLADOR 
use Maatwebsite\Excel\Facades\Excel;

ASOCIAR A UN METODO LA DESCARGA
return Excel::download( new UsersExport, 'users.xlsx');


CREAR VISTA CON TABLA PARA LO QUE DESEAS EXPORTAR 
reporteUsers.blade.php

INVOCAR 2 FUNCIONES DE EXCEL 
use Illuminate\Contracts\View\View;
use Maatwebsite\Excel\Concerns\FromView;


EJECUTAR METODO PARA ENVIAR DATOS 
public function view(): View
		{
			return View('exportUsers', [
				'users' => User::all()
			]);
			# code...
		}