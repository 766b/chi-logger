chi-logger
===
`chi-logger` is a simple logging middleware for [Chi](https://github.com/go-chi/chi) with support for `Zap` and `Logrus`

Installation
---

    go get github.com/766b/chi-logger

Usage with Logrus
---

    logger := logrus.New()
    
    r := chi.NewRouter()
    r.Use(middleware.RequestID)
    r.Use(middleware.RealIP)
    r.Use(chilogger.NewLogrusMiddleware("router", logger))
    ...

Usage with Zap
---

    logger, _ := zap.NewProduction()

    r := chi.NewRouter()
    r.Use(middleware.RequestID)
    r.Use(middleware.RealIP)
    r.Use(chilogger.NewZapMiddleware("router", logger))
    ...
