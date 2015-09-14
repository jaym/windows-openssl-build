
OPENSSL_VERSION = IO.read(File.expand_path("../OPENSSL_VERSION", __FILE__)).strip

desc "Build openssl #{OPENSSL_VERSION}"
task :build do
  Dir.chdir("./knap-build") do
    sh "./bin/knap-build.bat openssl -v #{OPENSSL_VERSION} --package -V"
  end
end

desc "Build openssl-fips"
task :build_fips do
  Dir.chdir("./knap-build") do
    sh "./bin/knap-build.bat openssl -v #{OPENSSL_VERSION}.fips --package -V"
  end
end
