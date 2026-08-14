This acts as middleware between the client and the server.
It is used to inspect, transform, or modify outgoing requests and incoming responses.

This example gets the responses and acts if these are errors(showing toasts):

```
export const errorInterceptor: HttpInterceptorFn = (req, next) => {
  const toast = inject(ToastService);
  return next(req).pipe(
    catchError(error => {
        if (error) {
            switch(error.status) {
                case 400:
                    toast.error(error.error);
                    break;
                case 401:
                    toast.error('Unathorized');
                    break;
                case 404:
                    toast.error('Not found')
                    break;
                case 500:
                    toast.error('Server error');
                    break;
                default:
                    toast.error('Something went wrong')
                    break;
            }
        }
        throw error;
    })
  );
};
```