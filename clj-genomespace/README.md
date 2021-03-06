# GenomeSpace with Clojure

This is a small test to access [GenomeSpace][1] from Clojure using the Java
API. This allows upload and download of files to GenomeSpace. GenomeSpace itself
makes these files available to Galaxy, GenePattern and other tools.

[1]: http://www.genomespace.org/

## Usage

Download Clojure libraries, the GenomeSpace CDK and start a REPL:

    $ lein deps
    $ wget http://genomespace.org/attachments/cdk_beta4_0.zip
    $ unzip cdk_beta4_0.zip
    $ cp CDK_beta4.0/lib/*.jar lib
    $ lein repl

From the REPL:

    user> (use 'clj-genomespace.core)
    user> (def client (get-gs-client "chapmanb" :password "password"))
    user> (gs-upload client "cdk-test" "/path/to/yourfile.vcf")
    user> (gs-download client "cdk-test" "yourfile.vcf")

## License

The code is freely available under the [MIT license][l1].

[l1]: http://www.opensource.org/licenses/mit-license.html
