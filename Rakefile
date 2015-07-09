
OPENSSL_VERSION = IO.read(File.expand_path("../OPENSSL_VERSION", __FILE__)).strip

desc "Build openssl #{OPENSSL_VERSION}"
task :build do
  Dir.chdir("./knap-build") do
    sh "./bin/knap-build.bat openssl -v #{OPENSSL_VERSION} --platform i686-mingw32 --package"
  end
end
