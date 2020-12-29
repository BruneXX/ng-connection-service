# Internet Connection Monitoring Service (Angular v11)

> Detects whether browser has an active internet connection or not in Angular application.

## Install

You can get it on npm.

```
npm install ngx-connection-service --save
```

## Usage

1. Inject `ConnectionService` in Angular component's constructor.
2. Subscribe to `monitor()` method to get push notification whenever internet connection status is changed.

```ts
import { Component } from '@angular/core';
import { ConnectionService } from 'connection-service';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  status = 'ONLINE';
  isConnected = true;

  constructor(private connectionService: ConnectionService) {
    this.connectionService.monitor().subscribe(isConnected => {
      this.isConnected = isConnected;
      if (this.isConnected) {
        this.status = "ONLINE";
      }
      else {
        this.status = "OFFLINE";
      }
    })
  }
}

```

## Demo

[Working demo](https://ngx-connection-service-demo.surge.sh/)

## License

[MIT License](https://github.com/BruneXX/ngx-connection-service/blob/master/LICENSE) © Bruno Binci
