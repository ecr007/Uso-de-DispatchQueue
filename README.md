# Uso de DispatchQueue

Source: https://www.raywenderlich.com/148513/grand-central-dispatch-tutorial-swift-3-part-1

# Asincrona: Cuando la carga se hace en segundo plano y no detiene ningun proceso

```

    DispatchQueue.global(qos: .userInitiated).async {
			
			if let u = URL(string: self.url){
				
				DispatchQueue.main.async {
					let res = URLRequest(url: u)
					
					DispatchQueue.main.async {
						self.objWeb.loadRequest(res)
					}
				}
			}
		}
    
```

# Sincrona: Cuando la carga se hace en primer plano

```

DispatchQueue.main.sync {

}

```

# Ejecutar un proceso despues de un tiempo

```

let when = DispatchTime.now() + 2 // change 2 to desired number of seconds
DispatchQueue.main.asyncAfter(deadline: when) {
   // Your code with delay
}

```

    
    
