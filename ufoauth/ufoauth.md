!SLIDE

    import unfiltered.jetty.Http
    import unfiltered.oauth._

    val stores = new OAuthStores {...}

    jetty.Http(8080)
      .filter(new OAuth(stores))
      .filter(new MyApp).run

!SLIDE
    /** what oauth depends on. 
      * you fill in the blanks */
    trait OAuthStores {
      val nonces: NonceStore
      val tokens: TokenStore
      val consumers: ConsumerStore
      val users: UserHost
    }
    
!SLIDE

    g8 softprops/unfiltered-oauth-client
    cd unfiltered-oauth-client && sbt update run
    
    g8 softprops/unfiltered-oauth-server
    cd unfiltered-oauth-server && sbt update run
    
!SLIDE

# {code}