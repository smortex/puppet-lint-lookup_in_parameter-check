require 'bundler/gem_tasks'
require 'rspec/core/rake_task'

RSpec::Core::RakeTask.new(:spec)

task default: :spec

begin
  require 'rubygems'
  require 'github_changelog_generator/task'

  GitHubChangelogGenerator::RakeTask.new :changelog do |config|
    config.header = "# Changelog\n\nAll notable changes to this project will be documented in this file."
    config.exclude_labels = %w{duplicate question invalid wontfix wont-fix skip-changelog modulesync}
    config.user = 'opus-codium'
    config.project = 'puppet-lint-lookup_in_parameter-check'
    config.future_release = Gem::Specification.load("#{config.project}.gemspec").version
  end
rescue LoadError
end