# Applying the patch
* First find your gem path for your ruby installation, mine was:
```sh
export GEM_INSTALL_PATH=~/.rvm/gems/ruby-2.7.1/gems
```

* First copy the files into the appropriate directory
```sh
cp response_middleware.rb.patch $GEM_INSTALL_PATH/faraday_middleware-0.12.2/lib/faraday_middleware/

cp options.rb.patch $GEM_INSTALL_PATH/faraday-0.15.4/lib/faraday/
```

* Then, apply the patches
```sh
cd $GEM_INSTALL_PATH/faraday_middleware-0.12.2/lib/faraday_middleware/
patch response_middleware.rb < response_middleware.rb.patch

cd $GEM_INSTALL_PATH/faraday-0.15.4/lib/faraday/
patch options.rb < options.rb.patch
```

* Now you should be able to run the rails server and tests without the warnings
