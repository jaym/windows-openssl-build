
OPENSSL_VERSION = IO.read(File.expand_path("../OPENSSL_VERSION", __FILE__)).strip

if ENV['fips'] == 'true'
  task :default => [:build_fips]
else
  task :default => [:build]
end

desc "Build openssl #{OPENSSL_VERSION}"
task :build do
  Dir.chdir("./knap-build") do
    sh "./bin/knap-build.bat openssl -v #{OPENSSL_VERSION} --package -V"
  end
end

desc "Build openssl-fips"
task :build_fips do
  Dir.chdir("./knap-build") do
    sh "./bin/knap-build.bat openssl-fips --package -V"
    sh "./bin/knap-build.bat openssl -v #{OPENSSL_VERSION}.fips --package -V"
  end
end
